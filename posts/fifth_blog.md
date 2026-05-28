---
title: Accessibility, Responsibility, and Evaluation Planning
date: 2026-05-22
author: Yun-Chih Lin
summary: This post considers how the Skill Match Finder prototype can be evaluated and how accessibility and responsible implementation can be built into the design.
tags:
  - a2
  - dev-blog
  - accessibility
  - evaluation
---

As the concept becomes more concrete, I need to consider how the prototype should be evaluated and what responsible implementation means in this context. Skill Match Finder asks users to provide information about what they can offer and what they want to learn. This information is not extremely sensitive, but it still relates to user identity, confidence, ability, and learning goals. The prototype should therefore avoid collecting unnecessary personal information and should make the interaction feel clear and manageable.

Accessibility is important because the feature relies on forms, buttons, cards, and result comparison. Each form input should have a visible label, such as “I can offer” and “I want to learn”. These labels should not be replaced by placeholder text because placeholders disappear when users type or select an option. Buttons should use specific action language, such as “Search for Matches”, “View Details”, and “Save Match”, rather than vague labels. This helps users understand what will happen next.

Keyboard accessibility is another key requirement. Users should be able to move through the form, select options, open match details, and save a match without relying on a mouse. The visual focus state should be clear so users can see where they are on the page. Match cards should also have a logical reading order, with the name first, then offered skill, wanted skill, match type, and action button.

The interface should not rely only on colour to communicate match quality. For example, mutual matches and partial matches can use different visual treatments, but they should also include text labels. This is important because users with colour vision differences may not interpret colour-coded information in the same way. The match explanation also supports accessibility because it gives users a written reason for each recommendation.

Responsible implementation also means limiting the scope of stored information. For this prototype, the system only needs skill preferences, exchange format, and saved match state. It does not need personal contact details, private messages, or detailed profiles. Since messaging is not part of the core feature, it can remain outside the prototype. This reduces complexity and avoids unnecessary data handling.

To evaluate the prototype, I would focus on whether users can complete the main flow without explanation. A simple usability test could ask users to create a skill profile, find a match, understand why the match was recommended, and save the result. After that, I would ask whether the match reason helped them trust the recommendation and whether any step felt unclear or unnecessary.

The main success measure is not whether users think the app has many features. The stronger measure is whether they can quickly understand the matching process and see the value of the recommendation. If users can move from input to result with confidence, the prototype will demonstrate the community’s unique feature effectively.