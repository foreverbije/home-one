---
layout: post
company: "Ridisi"
title: "Development of an augmented text editor targeting reading techers"
date: 2023-04-17 09:50:13 +0600
tags: ruby-on-rails devops
categories: [Case Study]
author: "Stéphane Akkaoui"
post_image: "/assets/images/case_studies/ridisi/logo.png"
show_categories: false
show_meta_info: false
show_comments: false
show_bottom_posts: false
show_bottom_tags: false
---

- - -
**TL;DR : Ridisi is a text editor helping teachers in creating augmented texts for strudents leqrning to read. When a sentence is typed, Ridisi automatically detect syllables, graphemes and phonemes and complete the text with different help like pictures representing the sound, marks of silent letters, complexe sounds or bezier curves to differentiate syllables. Forever Bije was (and still is) present for every step of the project, from ideation to development, hosting and maintainance.**
- - -
## 🧩 The initial problem
- - -
**Ridisi** is an association of 3 school teachers from Rennes. They have put together **a methodology to teach their student how to read by associating pictograms to phonemes** and displaying them on top of the corresponding graphemes when they print out a text for the class. This proved to be really successful and improved their student proficiency with reading skills compared to similar classes.

The difficulty was the time needed to create augmented texts with existing text editors (Word, Open Office, ...). Mannualy placing the pictograms and other help was tedious, and doing so for each student level (some need more help than other) is really time consuming. Existing tools, like the Open Office plugin LireCouleur, were not on par with the features, the precision nor the usability required by teaching children how to read.

They decided to build their own **SaaS product**.

![Ridisi home page](/assets/images/case_studies/ridisi/case-study-1.png)

- - -
## ✅ The solution
- - -

Forever Bije provided services in two steps :

\- first we helped them scope the project, define what was possible, size and cost required features.    
\- next, we took care of the development of the Ridisi software

The final product is a web application built with the Ruby On Rails framework, using no front end tools appart from Hotwire (Stimulus and Turbo). This ruby code handle everything from the user and session management, the folder and document processing, the grids and grid items configuration, and the student profils customization.

The Ridisi augmentation itself is done through heavy CSS and a Javascript parser and HTML builder.

![Ridisi grids](/assets/images/case_studies/ridisi/case-study-3.png)

**We build a parser that is able precisely ready a text and extract the following features for the French language**:

\- words extraction    
\- syllables spearation, counting and schema detection    
\- graphemes detection and counting    
\- phoneme assignation

From this internal text representation, an in depth **Trix customization** print out the analyzed text into HTML nodes of our own HTML5 tags: `<word>`, `<syllable>`, `<grapheme>`, each with specific attributes.

**A set of CSS rules decorate this HTML document** with the available helps:

\- slightly hide the silent letters    
\- underline complexe sounds (in alternance doshed and solid)    
\- describe syllables, either by a bézier curve or an alternance or blue and red colors    
\- separate triple sounds in syllables and numbers them from one to three    
\- display a pictograme representing a phoneme on top of the grapheme corresponding to chosen grids and grid customization    
\- increase word spacing, letter spacing, line gap and font size

![Ridisi text editor](/assets/images/case_studies/ridisi/case-study-2.png)

**Users of Ridisi can export their annotated documents as a PDF file**. This is done from the same HTML grap and CSS rules as the front end display, and uses HTML to PDF converter. Due to the advanced CSS usages, we tried different solution (both paid and in house) to acheive an acceptable result :

\- wkhtmltopdf: using internally an old version of QTWebkit, this engine doesn't handle advanced CSS rules. For instance, `border-radius` used to display bezier curves under syllables is broken in some cases.    
\- an in house deployement of headless Chromium: on top of other issues described in the next solution, this deployment was ressource intensive for our servers and too costly.    
\- a third party solution, PDFShift, based on headless Chromium: by getting ride of resources consomption and scalability issues, we kept here issues with Webkit print version of document using a custom `word-spacing` or `letter-spacing`. This caused Webkit to incorrectly wrap text at the end of the bounding box (or document).    
\- a third party solution, DocRaptor, based on a proprietary PDF rendering engine, PrinceXML. This is the solution currently used in production. It also had issues with `word-spacing` rules on unbreakable spaces, that we eleviated by cleaning them for classic spaces. This can still be problematic in front of punctuation marks that need a space before, when they end up at the end of a line, though.


- - -
## 💻 The stack
- - -

- **App**: Ruby on Rails
- **Database**: PostgreSQL
- **Testing**: Rspec, FactoryBot
- **Background Tasks**: ActiveJob
- **CSS**: SASS, Bulma
- **Javascript**: Stimulus, ActionCable, Vanilla Javascript
- **Hosting**: Scalingo
- **CI/CD & Project Management**: Gitlab

- - -
## 🚀 The results
- - -

In less than one year after the first discussions, we were able to deliver a tool that were up to the quality standards of our customers. **This application is daily used by more than 300 teachers** in France and Belgium, and this user base is growing continuously.

**Ridisi was recently rewarded by the French Education Ministry** with the EduUp label and received a grant to develop more features and deploy it in every French schools.

As of today, we are still working with Ridisi.

The Javascript engine analysing the French language is soon to be released in open source.
