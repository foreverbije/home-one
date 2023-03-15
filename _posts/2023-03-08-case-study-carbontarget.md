---
layout: post
company: "Carbon Target"
title: "A different approach to the Carbon Footprint"
date: 2023-03-08 12:06:13 +0600
tags: nodejs devops
categories: [Case Study]
author: "Vincent Gabou"
post_image: "/assets/images/case_studies/carbontarget/logo.jpg"
show_categories: false
show_meta_info: false
show_comments: false
show_bottom_posts: false
show_bottom_tags: false
---

- - -
**TL;DR : We worked for a year on a Javascript intensive project (StimulusJS) allowing anyone to prepare his/her carbon footprint in advance, with respect to a defined target.**
- - -
## 🧩 The initial problem
- - -
Personal Carbon Footprint Calculators are quite common nowadays, work well, and are usually rather advanced in terms of computations. The goal with **Carbon Target** was not to provide just another calculator but **offer a supplement with a different approach to the same topic**.

Carbon Target should provide an answer to the question : what would MY life be like, in a world where we all live under X tons of yearly carbon emission ? (where often X = 2)

- - -
## ✅ The solution
- - -

We built a simple looking single-page web application (the product is still at its MVP, - Minimum Viable Product -, stage) to try to answer this existential question in 2 steps :

1. **The user can set a "carbon target" in the form of a number of tons of yearly carbon emission X**

    ![Nanotrust Case Study 2](/assets/images/case_studies/carbontarget/case-study-1.png)

2. There are sliders corresponding to the main sources of carbon emissions a person can leverage in his/her everyday life. These **sliders are all dynamically linked**, which means that **Carbon Target will never allow to exceed the initial value of X**. This lets the user understand that should he/she want to consume more of something, a reduction needs to be done on another criteria.

    ![Nanotrust Case Study 3](/assets/images/case_studies/carbontarget/case-study-2.png)

- - -
## 💻 The stack
- - -

- **App**: Gulp
- **CSS**: SASS, Bulma
- **Javascript**: Stimulus
- **Hosting**: Personal Server
- **CI/CD & Project Management**: GitHub

- - -
## 🚀 The results
- - -

The site was officially launched in December of 2022. You can try it out and see what your life would be at 2 tons of annual carbon emissions : <a href="https://carbontarget.earth/" target="_blank">https://carbontarget.earth/</a>
