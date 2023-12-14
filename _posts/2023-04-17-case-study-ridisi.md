---
layout: post
company: "Ridisi"
title: "Development of an augmented text editor targeting reading teachers"
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
**TL;DR : Ridisi is a text editor helping teachers in creating augmented texts for students learning to read. When a sentence is typed, Ridisi automatically detects syllables, graphemes and phonemes. It then enriches the text with different elements like pictures representing the sound, marks of silent letters, complex sounds or bezier curves to differentiate syllables. Forever Bije was (and still is) present for every step of the project, from ideation to development, hosting and maintainance.**
- - -
## 🧩 The initial problem
- - -
**Ridisi** is an association of 3 school teachers from Rennes. They have put together **a methodology to teach their students how to read by associating pictograms to phonemes** and displaying them on top of the corresponding graphemes when they print out a text for the class. This proved to be really successful and improved their students proficiency with reading skills compared to similar classes.

The difficulty was the time needed to create augmented texts with existing text editors (Word, Open Office, ...). Manualy placing the pictograms and other elements was tedious, and doing so with respect to each student's level (some need more help than others) is really time consuming. Existing tools, like the Open Office plugin LireCouleur, were not on par with the features, the precision nor the usability required for teaching children how to read.

They decided to build their own **SaaS product**.

![Ridisi home page](/assets/images/case_studies/ridisi/case-study-1.png)

- - -
## ✅ The solution
- - -

Forever Bije provided services in two steps :

\- first we helped them scope the project, define what was possible, the size and cost of required features.
\- next, we took care of the development of the Ridisi software.

The final product is a web application built with the Ruby On Rails framework, using no front-end tools apart from Hotwire (Stimulus and Turbo). This ruby code handles everything from the user and session management, the folders and documents processing, the grids and grid items configuration, to the student profiles customization.

The Ridisi augmentation itself is done through heavy CSS and a Javascript parser and HTML builder.

![Ridisi grids](/assets/images/case_studies/ridisi/case-study-3.png)

**We built a parser that is able to precisely ready a text and extract the following features from the French language**:

\- words extraction
\- syllables spearation, counting and schema detection
\- graphemes detection and counting
\- phoneme assignation

From this internal text representation, an in depth **Trix customization** prints out the analyzed text into HTML nodes of our own HTML5 tags: `<word>`, `<syllable>`, `<grapheme>`, each with specific attributes.

**A set of CSS rules decorates this HTML document** with the available elements:

\- slightly hide the silent letters
\- underline complex sounds (switching between dashed and solid)
\- describe syllables, either by a bézier curve or an alternance of blue and red colors
\- separate triple sounds in syllables and number them from one to three
\- display a pictograme representing a phoneme on top of the grapheme corresponding to chosen grids and grid customizations
\- increase word spacing, letter spacing, line gap and font size

![Ridisi text editor](/assets/images/case_studies/ridisi/case-study-2.png)

**Users of Ridisi can export their annotated documents as a PDF file**.

This is done from the same HTML grap and CSS rules as the front-end display, and uses HTML to PDF converter. Due to the advanced CSS usages, we tried different solutions (both paid and in house) to achieve an acceptable result :

\- wkhtmltopdf: using internally an old version of QTWebkit, this engine doesn't handle advanced CSS rules. For instance, `border-radius` used to display bezier curves under syllables is broken in some cases.
\- an in house deployement of headless Chromium: on top of other issues described in the next solution, this deployment was ressource intensive for our servers and too costly.
\- a third party solution, PDFShift, based on headless Chromium: by getting rid of resources consumption and scalability issues, we still had issues with Webkit print version of document using a custom `word-spacing` or `letter-spacing`. This caused Webkit to incorrectly wrap text at the end of the bounding box (or document).
\- a third party solution, DocRaptor, based on a proprietary PDF rendering engine, PrinceXML. This is the solution currently used in production. It also had issues with `word-spacing` rules on unbreakable spaces, that we alleviated by replacing them by classic spaces. This can still be problematic in front of punctuation marks that need a preceding space, when they end up at the end of a line, though.

For this project, we worked closely with the amazing team at [Entreautre](https://www.entreautre.com) for all UX and UI design aspects of the product. [They provided invaluable advices and produced a nice interface that was simple and intuitive for our users.](https://www.entreautre.com/case-study/simplifier-le-travail-des-instituteur·ices-pour-renforcer-linclusion-a-lecole/).

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

In less than one year after the first discussions, we were able to deliver a tool that was up to the quality standards of our customers. **This application is used daily by more than 300 teachers** in France and Belgium, and this user base is growing continuously.

**Ridisi was recently awarded by the French Education Ministry** with the EduUp label and received a grant to develop more features and deploy it in every French schools.

As of today, we are still working with Ridisi.

The Javascript engine analysing the French language is soon to be released in open source.
