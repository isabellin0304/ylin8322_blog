---
title: Comparing Feature Concepts and Choosing Skill Match Finder
date: 2026-05-01
author: Yun-Chih Lin
summary: This post compares several possible community feature directions and explains why Skill Match Finder became the strongest option for the prototype.
tags:
  - a2
  - dev-blog
  - feature-selection
---

After defining the need for a more focused Bla+Bla community feature, I began comparing possible directions for the prototype. Since the A2 brief asks us to focus on the unique value of a specific community, I wanted to avoid designing a general social space that simply repeats standard functions such as posting, messaging, or user profiles. Those features may support a community, but they do not clearly show why the community needs a tailored application.

The community direction I am currently developing is a campus skill swap community. The basic idea is that students often have skills they can offer and skills they want to learn, but it can be difficult to find the right person through informal posts or large discussion spaces. A student may know photography and want to learn web design. Another student may know web design and want to learn photography. In a normal discussion board, these two users would need to search manually, compare posts, and judge whether there is a useful exchange. This creates unnecessary friction.

I considered three possible feature directions. The first was a simple skill request board, where students could post what they wanted to learn. This would be easy to implement and easy for users to understand, but it would mostly behave like a normal forum. It would rely on users to browse manually, so the application itself would not add much value. The second idea was a portfolio browsing feature, where students could display examples of their work and contact others. This could be visually engaging, but it would shift the focus toward self-promotion rather than mutual exchange. It would also require more media handling, which may increase the technical scope without directly supporting the main user need.

The third idea was a Skill Match Finder. This feature asks users what they can offer, what they want to learn, and what exchange format they prefer. The system then recommends possible matches and explains why each match works. This direction feels stronger because it responds directly to the problem of finding a relevant exchange partner. It also creates a clear interaction that is specific to this community, rather than relying on generic social platform behaviours.

I chose Skill Match Finder because it has a better balance between user value and implementation feasibility. It is technically meaningful because it requires structured data, matching rules, result ordering, and a clear interface. At the same time, it remains realistic for a prototype because the matching logic can begin with simple rule-based scoring rather than a complex recommendation system. This allows the prototype to demonstrate the core idea without becoming too large or unstable.

This decision also helps define the scope of the project. The prototype does not need to include a full chat system, detailed public profiles, reviews, or notifications at this stage. Those may become useful in a complete product, but the main assessment value comes from showing how the matching process works. For the next stage, I need to turn this chosen feature into a clear user flow, so that the interaction can be tested and later implemented in the Bla+Bla prototype structure.