---
layout: post
company: "Nanotrust"
title: "Self Sovereign Identity, Verifiable Credential, Blockchain & Web development"
date: 2023-03-10 12:06:13 +0600
tags: ruby-on-rails web-design devops
categories: [Case Study]
author: "Vincent Gabou"
post_image: "/assets/images/case_studies/nanotrust/logo.png"
show_categories: false
show_meta_info: false
show_comments: false
show_bottom_posts: false
show_bottom_tags: false
---

- - -
**TL;DR : We worked with Nanotrust for 5 months on a complex project mixing the implementation of a Decentralized Identity (DID) provider, a Verifiable Credential (VC) workflow anchored on the Tezos Blockchain, and an administration web application allowing Users to create, manage and share their Credentials.**
- - -
## 🧩 The initial problem
- - -
**Nanotrust** is a young company aiming to leverage new technologies (_decentralized ID_, _Verifiable Credentials_ and _Blockchain_) to ease the **generation, authentication, and sharing of any kind of documents**. The goal is to allow an Issuer to generate a unique, instantly verifiable, non-fungible document and assign it to an Owner who can then share it with the world. That certificate can be, for instance, a diploma, a proof of purchase, a pay slip, etc.

The team already had a senior developer on board, but they wanted to go faster and develop an MVP (Minimum Viable Product) in just a few months. This is where Forever Bije came in.

![Nanotrust Splash Screen](/assets/images/case_studies/nanotrust/case-study-1.jpeg)

- - -
## ✅ The solution
- - -

From the initial brief, we identified 3 main themes that we isolated in microservices :

1. **An Authentication micro-service**

    We shared with the Nanotrust team strong beliefs in open standards, so we used the famous OAuth2 and OpenID protocols to manage Authentication and Authorization, and packaged it in a micro-serviced provider we called NanoAuth.

    ![Nanotrust Case Study 2](/assets/images/case_studies/nanotrust/case-study-2.png)

2. **A web wallet service to generate and store Verifiable Credentials (VC), with an optional anchoring in the Tezos Blockchain**

    We built a web wallet similar to those existing for cryptocurrencies but built to securely store VC. This required managing a Decentralized Identity, which we implemented with a wrapper on top of the didkit C library in Ruby. This toolkit allowed us to implement a _Verifiable Credential workflow_.

    The anchoring of the VC on a blockchain was a feature required by NanoTrust, so we implemented in Ruby a wallet feature to communicate with the Tezos Blockchain (generating and signing transactions, originating and controlling smart contracts).

    We called this service NanoWallet.

    ![Nanotrust Case Study 3](/assets/images/case_studies/nanotrust/case-study-3.png)

3. **A web interface to create an account, issue, receive, manage and share credentials.**

    This last layer is a more general Ruby on Rails-backed website that ties everything together and communicates with the other micro-services via API. It is the _client-facing application_ that allows Nanotrust to deliver on its promise: allow the generation, management and sharing of unique & verifiable certificates, written on the Tezos Blockchain.

    The platform was designed & integrated by Forever Bije, who produced a UI toolkit and designs of the pages.

    ![Nanotrust Case Study 4](/assets/images/case_studies/nanotrust/case-study-4.png)

    ![Nanotrust Case Study 5](/assets/images/case_studies/nanotrust/case-study-5.png)

- - -
## 💻 The stack
- - -

- **App**: Ruby on Rails, Rust, C
- **Database**: PostgreSQL, Redis
- **Authorization**: OAuth2
- **Blockchain**: RPC Protocol, Tezos, Michelson, Smartpy
- **Testing**: Rspec, FactoryBot
- **Background Tasks**: ActiveJob, Sidekiq
- **CSS**: SASS, Bulma
- **Javascript**: Stimulus, ActionCable
- **Payment**: Stripe
- **Hosting**: Scalingo
- **CI/CD & Project Management**: Gitlab

- - -
## 🚀 The results
- - -

After an intensive and effective collaboration, the team **launched the Nanotrust service with success and on time**.

It is now **running in production** and gaining traction, starting with a collaboration with we are_ (a French cultural club gathering 1000+ members of the Tech world) which uses Nanotrust-generated certificates for their members' subscriptions and fidelity program.
