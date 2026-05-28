---
title: Planning the Data and Matching Logic
date: 2026-05-15
author: Yun-Chih Lin
summary: This post outlines the data structure and rule-based matching logic needed to support the Skill Match Finder prototype.
tags:
  - a2
  - dev-blog
  - technical-planning
---

Once the user flow became clearer, I started thinking about the data and logic needed to make Skill Match Finder work. This step is important because the feature depends on more than visual interface design. The prototype needs to compare user inputs with existing student data and return meaningful matches. If the data structure is unclear, the interface may look complete but the core function would not be convincing.

The main data objects in this prototype are users, skills, exchange formats, and saved matches. Each user needs a name, a list of skills they can offer, a list of skills they want to learn, and their preferred exchange format. For example, one user may offer “Web Design”, want to learn “Photography”, and prefer online or in-person exchange. Another user may offer “Photography”, want to learn “Web Design”, and prefer in-person exchange. These two users would form a strong mutual match.

I am planning to begin with seed data rather than a fully dynamic database. This is a practical scope decision. Seed data allows me to test the matching logic and interface without spending too much time building account creation, authentication, or large-scale user management. Since the Bla+Bla platform already handles core services such as sign-in, the prototype can focus on the unique community feature. Later, the same structure could be connected to real user data.

The matching logic can start with rule-based scoring. A mutual match receives the highest score when another user can teach what the current user wants to learn and also wants to learn what the current user can offer. A one-way match occurs when another user can teach the desired skill, even if they do not need the current user’s offered skill. A format match can increase the score if both users prefer the same exchange method, such as online or in-person.

This approach is simple, but it is useful for a prototype because it makes the system behaviour explainable. I can show why a person appears as a strong match, rather than presenting recommendations as a black box. This also supports the Match Detail screen, where users can read a short reason for each recommendation. The explanation is part of the user experience, not just a technical output.

Technically, I want to separate the matching logic from the interface components. The form component should collect user input. The results component should display matched users. The matching function should handle comparison and scoring. Keeping these responsibilities separate will make the code easier to maintain and test. It also supports a clearer project structure, because the interface and logic will not be mixed together in one large component.

The main trade-off is that rule-based matching is less flexible than a more advanced recommendation system. However, it is more appropriate for this assignment because it can be implemented reliably within the available scope. A stable, understandable matching feature is more valuable for this prototype than an ambitious system that is difficult to complete or explain.