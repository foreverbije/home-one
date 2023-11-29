---
layout: post
company: "Ecov"
title: "Modernizing Ruby on Rails Applications"
date: 2023-11-29 18:45:13 +0600
tags: ruby-on-rails ruby
categories: [Case Study]
author: "Stéphane Akkaoui"
post_image: "/assets/images/case_studies/ecov/logo.png"
show_categories: false
show_meta_info: false
show_comments: false
show_bottom_posts: false
show_bottom_tags: false
---

- - -
**TL;DR : ForeverBije successfully upgraded Ecov's Ruby on Rails applications over two months, methodically migrating from Ruby 2.7 and Rails 5.2 to Ruby 3.2 and Rails 7.0. The process involved a detailed initial audit, systematic updates of gems, configurations, and adherence to new naming conventions. Despite challenges like serialization changes and unsupported gems, ForeverBije effectively resolved these issues, enhancing the performance and maintainability of Ecov's digital infrastructure. This project exemplifies ForeverBije's technical expertise and adaptability in software upgrades.**
- - -
## 🧩 The initial problem
- - -
Ecov, an innovative company transforming individual cars into public transport services, faced a significant challenge: **upgrading their outdated Ruby on Rails application**. ForeverBije stepped in to lead this crucial technological transition.
- - -
## ✅ The solution
- - -

**Audit and Assessment**: Our initial two-day audit meticulously evaluated custom and open-source gems for migration risks, assessed test coverage and quality, and ensured the development environment was primed for testing. This foundational step set the stage for the upgrade.

**Migration Process**: Over two months, our team dedicated 25 days to **meticulously upgrade one large shared library and nine applications** from Ruby 2.7 to 3.2 and Rails 5.2 to 7.0. We approached Rails migration gradually, transitioning first to 6.0, then 6.1, and finally to 7.0. After each step, we rigorously tested and upgraded necessary gems, ensuring seamless functionality before advancing. The Ruby migration was tackled in one ambitious leap from 2.7 to 3.2, **with extensive testing and fixes** applied throughout the process.

**Our methodology was systematic**: updating versions in Gemfile, gemspec, .ruby-version, and Dockerfile; adjusting default configurations in config/application.rb; and modifying schema.rb to align with Rails version changes. Additionally, we restructured class, file, and directory names to adhere to Zeitwerk's conventions.

**Challenges and Solutions**: The upgrade journey wasn't without its hurdles. We navigated through various challenges, including adapting to JSON serialization for Date, Time, or BigDecimal classes, addressing the precision changes in DateTime columns, and adapting to the updated ActionDispatch content_type format. **The transition to Zeitwerk's new naming convention required thoughtful directory architecture modifications**. Some gems were no longer supported, prompting us to creatively fix their versions or patch them. Additionally, the move away from CoffeeScript necessitated converting scripts to standard JavaScript.

**Results and Impact**: The successful migration brought Ecov's applications up to speed with the latest technological standards, enhancing both performance and future maintainability. **This upgrade has positioned Ecov to better serve their customers** with a more robust and efficient digital infrastructure.


- - -
## 💻 The stack
- - -

- **App**: Ruby on Rails
- **Database**: PostgreSQL
- **Testing**: Rspec, FactoryBot
- **Background Tasks**: Sidekiq
- **Hosting**: Custom
- **CI/CD & Project Management**: Gitlab

- - -
## 🚀 The results
- - -

The collaboration between Ecov and ForeverBije exemplifies **our commitment to technical excellence and our ability to adapt to evolving software landscapes**. This project not only modernized Ecov's technological backbone but also reinforced their infrastructure improving the applications performance and reliability. **ForeverBije's expertise in handling complex software upgrades** has once again proven pivotal in advancing our client's operational capabilities.