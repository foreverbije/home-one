---
layout: post
company: "Simplébo"
title: "IT Consulting & Development"
date: 2023-03-09 12:06:13 +0600
tags: ruby-on-rails audit
categories: [Case Study]
author: "Vincent Gabou"
post_image: "/assets/images/case_studies/simplebo/logo.png"
show_categories: false
show_meta_info: false
show_comments: false
show_bottom_posts: false
show_bottom_tags: false
---

- - -
**TL;DR : We've been working with Simplébo for 2 years on two aspects of IT. We first audited the codebase & organization of one of the two dev teams there, gave our feedback & advice as "outsiders". We then helped with the implementation of these advice, better unit testing, code cleaning, etc. by being involved in the daily run of product features.**
- - -
## 🧩 The initial problem
- - -
**Simplébo** is a SaaS helping entrepreneurs and independents to build their own website and be visible on plenty of mediums online. They aim to alleviate that task by leaving clients free to edit their site as they wish, by giving them a centralized interface to manage their online presence, but also by providing a personalized assistance to make their websites unique.

When we met Simplébo, their product was **already running in production**, with **thousands of clients using it**. However, because the coding started 8 years prior, _the codebase grew big_ and some parts of the codebase inevitably _accumulated a technical debt_. This debt was holding the progress and potential scaling back, both in terms of code & team size.

![Simplebo Splash Screen](/assets/images/case_studies/simplebo/case-study-1.png)

- - -
## ✅ The solution
- - -

We articulated our work in 3 phases to help Simplébo benefit from our years of experience in web development :

1. **Audit the entire team's codebase.**

    We went through the folder tree of the code repository, observed how the team was working together, and interviewed Simplébo's CTO about the IT infrastructure (servers, databases, logs, APIs, etc.). _We produced a discovery report_ listing our observations and the relevant advice we could give to improve coding & workflow, and we worked with the CTO to prioritize tasks.

2. **Introduce a culture of unit testing.**

    One of the main discoveries we made in phase 1 was an obviously light culture of testing, resulting in _a lack of unit testing_ in some parts of the codebase and a great improvement potential in the tested parts. We view it as pivotal for scaling up codebase & team size, but also for the developers well being. We helped kickstart a better culture by making a clean sweep on the tests, setting up a more suitable testing environment and writing tests for the most important resources/controllers in the codebase. This resulted in a short presentation that we made to the team, _to get everyone involved and up to speed with best practices_.

3. **Develop various features for the core application.**

    We were tasked by the team's CTO on a variety of features, mostly sensitive ones, with the idea of implementing the advice we gave in Phase 1. Our work around payments and the overhaul of the Invoicing system are the most impactful features we got to work on.

- - -
## 💻 The stack
- - -

- **App**: Ruby on Rails
- **Database**: MySQL, Redis
- **Testing**: Rspec, FactoryBot
- **Background Tasks**: DelayedJob
- **CSS**: SASS
- **Javascript**: jQuery, Stimulus
- **Hosting**: AlwaysData
- **Project Management**: Notion
- **CI/CD**: GitHub

- - -
## 🚀 The results
- - -

After a year of collaboration, the platform **has over 3000 quality unit tests** centered around key features, which is a **testament to the new testing culture in the team**. The team has also used our testing best practices presentation and shared it with the second development team at Simplébo, further instilling that culture at more levels.

Our development work on features _is almost entirely running in production_. We are currently working on merging our biggest one to date on making a self-sufficient & portable Invoicing system.
