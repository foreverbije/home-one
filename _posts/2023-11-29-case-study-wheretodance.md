---
layout: post
company: "Where to Dance"
title: "Web Platform Development"
date: 2023-11-29 19:15:00 +0600
tags: ruby-on-rails web-design devops
categories: [Case Study]
author: "Vincent Gabou"
post_image: "/assets/images/case_studies/wheretodance/logo.jpg"
show_categories: false
show_meta_info: false
show_comments: false
show_bottom_posts: false
show_bottom_tags: false
---

- - -
**TL;DR : We've been working with Where to Dance since the summer of 2023 on a mobile-first web application enabling users to find dance events near them, wherever they are ([https://www.wheretodance.fr](https://www.wheretodance.fr)). We've been involved in the specifications stage, the design, project management, all the way to the development stage of this app.**
- - -
## 🧩 The initial problem
- - -
**Where to Dance** is an initiative created by **Vidal F.** who approached us with a strong will to solve the problem he was facing when travelling abroad: where can I find a cool dance event near me ?

He felt he wasn't the only one with this problem, and wanted to create an online service allowing fellow dancers to do just that, with the added bonus of letting event organizers add their own events to both promote them and feed the service's catalogue.

- - -
## ✅ The solution
- - -

We developed a web platform called **Where to Dance** which addressed this issue with the following main features:

- **A User account that can be used by**
  - **Event goers looking for existing events** (an account is not necessary for the search part, but is required to purchase tickets to events)

    ![Wheretodance Case Study 1](/assets/images/case_studies/wheretodance/case-study-1.webp)

  - **Event organizers wanting to create** (with dates, a poster, a description, prices, links to ticket purchase, etc.) and **manage events** (edition, duplication, deletion)

    ![Wheretodance Case Study 2](/assets/images/case_studies/wheretodance/case-study-2.webp)

- An **interactive map** allowing users to browse for events directly, to use the "**Locate me**" feature to access events near their position, and to see previews of those events straight from the map.

  ![Wheretodance Case Study 3](/assets/images/case_studies/wheretodance/case-study-3.webp)

- A **complete fulltext search & filtering** allowing users to search for events with complex queries, including text, dates, dance styles and price ranges

  ![Wheretodance Case Study 4](/assets/images/case_studies/wheretodance/case-study-4.webp)

- The **ability to favorite an event** (via the heart icon), and access favorite events from the User's profile.

  ![Wheretodance Case Study 5](/assets/images/case_studies/wheretodance/case-study-5.webp)

- A **fully internationalized application with 2 languages currently available** (English and French), making the addition of new languages easy.

- - -
## 💻 The stack
- - -

- **App**: Ruby on Rails
- **Database**: PostgreSQL, Redis
- **Testing**: Rspec, FactoryBot
- **Background Tasks**: ActiveJob, Sidekiq
- **CSS**: TailwindCSS
- **Javascript**: StimulusJS, AlpineJS
- **Hosting**: Scalingo
- **Emailing** : Brevo
- **Assets hosting** : Scaleway
- **Error reporting** : Sentry
- **CI/CD & Project Management**: Gitlab

- - -
## 🚀 The results
- - -

After a few months of close collaboration, we **successfully delivered a first version** of the Where to Dance service in compliance with the initial specifications paper.

Our client is **very happy with the results** and wants to continue the site development with Forever Bije. Improvements are set to arrive in the coming months, as iterations are made and new versions of the application deployed.

You can find the website here : [https://www.wheretodance.fr](https://www.wheretodance.fr)