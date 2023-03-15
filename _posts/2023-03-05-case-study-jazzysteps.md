---
layout: post
company: "Jazzy Steps"
title: "Online Dance Classes platform"
date: 2023-03-05 12:06:13 +0600
tags: ruby-on-rails
categories: [Case Study]
author: "Vincent Gabou"
post_image: "/assets/images/case_studies/jazzysteps/logo.jpg"
show_categories: false
show_meta_info: false
show_comments: false
show_bottom_posts: false
show_bottom_tags: false
---

- - -
**TL;DR : We worked with Jazzy Steps for 6 months on a multi-tenant dance classes SaaS. The platform's goal is to allow anyone to launch his/her own online dance school and offer video series & subscription payments to students on a dedicated platform.**
- - -
## 🧩 The initial problem
- - -
*Jazzy Steps* is the twin sister company of Jazzy Feet, a Parisian dance school specialized in Swing dancing and Lindy Hop. They wanted to offer online classes but the solutions available at the time didn't meet their needs, which meant they had to develop their own platform. They also wanted to be able to sell such a platform to other schools if there were an opportunity for it.

Jazzy Steps was seeking external help to **delegate the back-end bootstrapping of such a platform**, and was set to take over the code to finish integrating the website. Forever Bije was contracted for that first phase of the project.

![Jazzy Steps Splash Screen](/assets/images/case_studies/jazzysteps/case-study-1.png)

- - -
## ✅ The solution
- - -

We developed a web platform called **Classers** which addressed this task by allowing anyone to access the following features :

1. **Create a Structure**, specify the _Teachers_, _Disciplines & Levels_ of that structure, and **configure the Stripe Integration** to be able to bill future students via subscriptions.

    ![Jazzy Steps Case Study 2](/assets/images/case_studies/jazzysteps/case-study-2.png)

2. **Administrate the Structure** by creating Courses, managing Students, and uploading teaching videos.

    ![Jazzy Steps Case Study 3](/assets/images/case_studies/jazzysteps/case-study-3.png)

3. **Display every created resources in a dashboard**, with _pagination & multi-criteria filtering_ to find specific Courses.

    ![Jazzy Steps Case Study 4](/assets/images/case_studies/jazzysteps/case-study-4.png)

4. **Have every teaching video displayed in a customized video player** with _Loop mode, Time Markers & Playback Speed management_ features.

    ![Jazzy Steps Case Study 5](/assets/images/case_studies/jazzysteps/case-study-5.png)

5. Have a **Comment section** below every video with _Replies, Mentions & Notifications_ features.

- - -
## 💻 The stack
- - -

- **App**: Ruby on Rails
- **Database**: PostgreSQL, Redis
- **Testing**: Rspec, FactoryBot
- **Background Tasks**: ActiveJob, Sidekiq
- **Javascript**: Stimulus, ActionCable
- **Video player**: Plyr
- **Hosting**: Scalingo
- **CI/CD & Project Management**: Gitlab

- - -
## 🚀 The results
- - -

We **successfully delivered the Classers platform** and the Jazzy Steps developer took over to finish its integration.

Classers is **currently running in production** and was used to create the **Jazzy Steps school**, available here : <a href="https://jazzy-steps.com/" target="_blank">https://jazzy-steps.com/</a>
