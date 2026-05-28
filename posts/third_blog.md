---
title: Turning Skill Match Finder into a User Flow
date: 2026-05-08
author: Yun-Chih Lin
summary: This post explains how the chosen feature can be structured as a clear user flow from profile input to saved matches.
tags:
  - a2
  - dev-blog
  - user-flow
---

After choosing Skill Match Finder as the central feature, the next design challenge was to turn the concept into a clear user flow. The main risk at this stage is making the prototype feel too broad. A campus skill swap community could easily include many features, such as messaging, portfolios, ratings, saved posts, group sessions, or event scheduling. However, including too many of these would make the prototype less focused. The goal is to show the core value of the community through one strong interaction.

The user flow I am planning has five main screens: Community Entry, Create Skill Profile, Match Results, Match Detail, and Saved Matches. This structure keeps the experience focused on one task: helping a student find a relevant skill exchange partner. Each screen has a specific purpose, and each one moves the user closer to that outcome.

The Community Entry screen introduces the purpose of the feature. It should quickly explain that users can exchange what they know and find what they want to learn. I do not want this screen to behave like a full homepage with many navigation choices. Its main role is to guide the user into the matching process. A single primary action, such as “Find a Match”, should be enough.

The Create Skill Profile screen is where the user provides the information needed for matching. The essential inputs are: what the user can offer, what the user wants to learn, and their preferred exchange format. This screen matters because the quality of the recommendations depends on the quality of the input. The interface should make the categories obvious and easy to complete. Dropdowns or selectable cards may work better than long text fields because they keep the data consistent and make the matching logic easier to implement.

The Match Results screen shows the recommended people. Each result card should include the person’s name, what they can teach, what they want to learn, and the type of match. For example, a mutual match should be visually and textually distinct from a partial match. This allows users to compare results quickly without opening every profile.

The Match Detail screen explains why a match works. This is important because the prototype should not only display names; it should show the reasoning behind the recommendation. A short explanation such as “You can teach what Maya wants to learn, and Maya can teach what you want to learn” makes the system more transparent and easier to trust.

The Saved Matches screen completes the flow. It gives the user a simple way to keep track of useful matches and continue searching. I am treating this as a small but important part of the prototype because it gives the interaction a clear end point.

This flow supports the project scope well. It avoids generic platform features and focuses on the unique matching process. The next step is to plan what data is required to make this flow work, especially how users, skills, preferences, and match types should be represented in code.