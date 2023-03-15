---
layout: post
company: "Madeinvote"
title: "Web Platform Development"
date: 2023-03-07 12:06:13 +0600
tags: ruby-on-rails web-design devops
categories: [Case Study]
author: "Vincent Gabou"
post_image: "/assets/images/case_studies/madeinvote/logo.jpg"
show_categories: false
show_meta_info: false
show_comments: false
show_bottom_posts: false
show_bottom_tags: false
---

- - -
**TL;DR : We worked with Madeinvote for 1,5 years on a complex project leading to the development of a API-intensive Back-Office like web platform. The platform's goal is to optimize workflow & help their team do on Madein360 the tasks they had to use 3 different services to complete.**
- - -
## 🧩 The initial problem
- - -
**Madeinvote** is a company specialized in conducting surveys and marketing studies for their clients, mostly in the Retail and Real Estate verticals. They build surveys, make sure they are properly taken buy end-customers, and gather insights/results which they then provide to their clients.

When Madeinvote got into contact with us, their main problem was using too many external services for a single project/client. Switching between services meant friction, time unefficiently used and thus revenue losses.

![Madeinvote Splash Screen](/assets/images/case_studies/madeinvote/case-study-1.png)

- - -
## ✅ The solution
- - -

We developed a web platform called **Madein360** which addressed this issue by allowing the Madeinvote team to conduct the entirety of a project on a single platform, using the external services' APIs under the hood:

1. **build & manage complex surveys (Voxco API)**

    **Voxco** is a service allowing clients to create complex surveys with 20+ question types, logic between question to allow for different user experiences for a given survey, host surveys, etc. **We created a DSL** allowing Madeinvote to create surveys **entirely through a text editor on Madein360**, and connected it to the Voxco API.

    ![Madeinvote Case Study 2](/assets/images/case_studies/madeinvote/case-study-2.jpeg)

2. **promote the created surveys with social ads (Meta Business API)**

    Once a survey is created, it needs to be pushed to the relevant audience. **Meta Business** allows to do just that with the use of Facebook & Instagram ads, and provides various stats (reach, engagement, money spent, etc). **We have coded a complete interface allowing to create the relevant resources** (Campaigns, Adsets, Ads, Audiences) through the Meta Business API directly from the Madein360 platform, and get ads statistics in our in-house dashboard.

    ![Madeinvote Case Study 3](/assets/images/case_studies/madeinvote/case-study-3.jpeg)

3. **fetch & display survey analytics (DATAVIV' API)**

    **DATAVIV'** is a data visualization service. Madeinvote used it by feeding it Voxco and Meta Business stats, and outputting pretty slides. We coded a connector doing that automatically, by formatting the data and sending it to DATAVIV' through their API.

Because those 3 APIs are deeply linked with Madein360, concurrency, load management, synchronization & performance were at the core of this challenging project.

The platform was designed & integrated according to the visual identity of Madeinvote's main front-facing website. To prepare this, Forever Bije produced a UI toolkit and designs of the pages.

- - -
## 💻 The stack
- - -

- **App**: Ruby on Rails
- **Database**: PostgreSQL, Redis
- **Testing**: Rspec, FactoryBot
- **Background Tasks**: ActiveJob, Sidekiq
- **CSS**: SASS, Bulma
- **Javascript**: Stimulus, ActionCable
- **Hosting**: Scalingo
- **CI/CD & Project Management**: Gitlab

- - -
## 🚀 The results
- - -

After a year and a half of close collaboration, **we successfully delivered a version of the platform** in accordance with the initial specifications paper at the end of 2022.

The **platform is still running in production** and development is being carried on by 2 in-house Madeinvote developers which we helped recruit & train.
