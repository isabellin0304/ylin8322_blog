---

title: Final Reflection on the Skill Swap Prototype
date: 2026-05-29
author: Yun-Chih Lin
summary: A final reflection evaluating the performance, user experience, accessibility, functional requirements, and development process of my A2 Web App Prototype.
tags:

* a3
* reflection
* evaluation
* web-app-prototype

---

For my A2 Web App Prototype, I built **Campus Skill Swap**, a Bla+Bla community prototype centred on a feature called **Skill Match Finder**. The purpose of this feature is to help students find potential skill exchange partners by comparing what they can offer, what they want to learn, and their preferred exchange format. Earlier in the project, I framed the main value of the prototype around matching rather than general social interaction. Looking back at the final version, I think this was the right scope decision because the prototype is strongest when it focuses on one clear interaction: moving a user from a skill need to a suggested exchange partner.

To evaluate the application, I tested the main user flow locally and reviewed the interface against a small accessibility and usability checklist. The evidence below summarises the main tasks I tested and the accessibility checks I used to guide my reflection. This evaluation is not a full deployment-scale assessment, but it gave me enough information to understand what the prototype currently does well and where it would need more development.

## Evidence 1: Task Walkthrough Results

| Task                               | Expected Result                                                  | Actual Result           | Notes                                                                                |
| ---------------------------------- | ---------------------------------------------------------------- | ----------------------- | ------------------------------------------------------------------------------------ |
| Open homepage and enter Skill Swap | User can find the prototype entry point | Passed | The homepage links clearly to the Skill Swap feature. |
| Complete the skill matching form | User can select offered skill, wanted skill, and exchange format | Passed | Form fields worked as expected and submitted successfully. |
| Search for a match | Results page shows relevant skill matches | Passed | A Photography → Web Design search returned Maya as a mutual match. |
| View match details | User can inspect a specific match | Passed | Detail page showed the selected user’s offered skill, wanted skill, format, and bio. |
| Save a match | Saved match appears in Saved Matches | Passed | Saved match was stored in the local SQLite database and displayed on the saved page. |
| Save the same match twice | Saved list should not show duplicates | Passed after refinement | Duplicate saved matches were prevented in the model logic. |

## Evidence 2: Accessibility and Usability Checklist

| Check                                 | Result                  | Reflection                                                                                                                                        |
| ------------------------------------- | ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| Visible form labels                   | Passed                  | The matching form uses visible labels for offered skill, wanted skill, and exchange format.                                                       |
| Clear button text                     | Passed                  | Buttons use action-based labels such as “Find a Match”, “Search for Matches”, and “Save Match”.                                                   |
| Match information clarity             | Passed                  | Match cards show name, offered skill, wanted skill, format, match type, and match reason.                                                         |
| Colour not used as the only indicator | Passed                  | Match type is communicated through text labels, not only styling.                                                                                 |
| Keyboard navigation                   | Basic pass              | Links, buttons, selects, and radio inputs can be reached through standard keyboard navigation.                                                    |
| Duplicate saved matches               | Passed after refinement | The system now checks whether a match has already been saved before inserting a new record.                                                       |
| Contrast and visual polish            | Needs further checking  | The interface uses clear cards and warm contrast, but a formal Lighthouse or WCAG contrast check would be useful before a final deployed version. |

## Performance and Technical Behaviour

In terms of technical behaviour, the prototype performs reliably within its current scope. The main flow loads quickly on localhost, and the matching process responds immediately after the form is submitted. This is partly because the prototype uses a small SQLite seed dataset and a simple rule-based matching function. The system does not need to process large amounts of data, call external APIs, or wait for complex recommendation calculations. As a result, the experience feels direct and responsive. Since my evaluation was conducted locally rather than on a deployed public server, the performance findings mainly reflect development testing rather than real deployment conditions.

The rule-based matching approach was a useful technical decision for this stage. A mutual match is created when another profile offers the skill the current user wants to learn and also wants to learn the skill the current user can offer. A one-way match appears when another user can teach the desired skill, and a partial match can still appear when there is some useful overlap. This logic is simple enough to test and explain, while still demonstrating the unique value of the application. The results page also shows match explanations, so the user can see why each person was recommended.

One weakness is that the performance evaluation is limited by the small test dataset. The application performs well with the current seed data, but this does not prove how it would behave with hundreds or thousands of skill profiles. If the project continued, I would need to test the matching logic with a larger dataset and consider whether the current scoring approach should be optimised or moved into more structured database queries. At the moment, the technical behaviour is suitable for a prototype, but it has not yet been tested as a production-scale matching system.

Another issue I found during testing was duplicate saved matches. At first, saving the same match multiple times caused the same person to appear more than once in the Saved Matches page. This was not a major performance issue, but it revealed a data handling problem. I fixed this by checking whether the match had already been saved before inserting a new record, and I also used a distinct selection when displaying saved matches. This small refinement made the application behave more like a real product because the saved list now reflects meaningful user choices rather than repeated button presses.

## User Experience and Accessibility

The strongest part of the user experience is the clarity of the main flow. The user begins at the homepage, enters the Skill Swap feature, completes a short form, receives match results, views a match in more detail, and saves useful matches. This sequence supports the intended user goal without requiring many decisions. The interface does not ask users to browse a large community feed or manually search through posts. Instead, it guides them through one focused task.

The match results page became more effective after I added match reasons. Before that refinement, the results were functional but less transparent. Users could see names and skills, but they had to infer why each match appeared. By adding written explanations, the system became easier to trust. For example, a mutual match can be explained in plain language: the user can teach Maya Photography, and Maya can teach the user Web Design. This supports the original aim of the prototype because the feature is not only finding people; it is helping users understand the relevance of those people.

The form design also supports usability. The labels “I can offer”, “I want to learn”, and “Preferred format” are visible and direct. The buttons use action-based wording, which helps users predict what will happen next. The page structure is also simple, with one major task per screen. This is important because the prototype is meant to reduce friction, not add another complicated social platform experience.

Accessibility is partially addressed in the current version. The form uses labels, match types are shown in text, and the interface does not rely only on colour to communicate meaning. Because the prototype uses standard HTML links, buttons, selects, and radio inputs, the main interactive elements should support basic keyboard navigation. However, I would still need to complete a more formal keyboard test before treating this as fully evaluated accessibility evidence. However, I would still treat accessibility as an area for further work. I have not yet completed a formal Lighthouse audit or WCAG contrast check, and the visual style should be tested more carefully. The warm colour palette makes the prototype feel cohesive, but visual appeal alone is not enough. A final version should verify colour contrast, focus visibility, and screen reader structure more thoroughly.

## Functional Requirements Revisited

The final prototype meets the main functional requirements I identified during planning. The essential requirement was to create a guided matching feature for a campus skill swap community. To support this, the user needed to be able to select an offered skill, select a wanted skill, choose an exchange format, receive relevant matches, understand the reason for those matches, view details, and save useful results. These core requirements are present in the final version.

The project also confirmed that some originally possible features were optional rather than essential. A full chat system, detailed user profiles, notifications, ratings, and uploaded portfolios could all support a complete skill swap platform, but they were not necessary for demonstrating the standout feature. Leaving them out helped keep the prototype stable and focused. This was important because the A2 brief prioritised the unique community feature rather than recreating standard platform functions.

Looking back, I think the initial requirements were mostly realistic because they centred on one interaction. The most useful refinement was recognising that “save match” needed a duplicate prevention rule. I originally treated saving as a simple action, but testing showed that even small data behaviours affect how trustworthy the application feels. This changed my understanding of functional completion. A feature is not complete just because the button works once; it also needs to behave sensibly when users repeat actions or use the system in slightly unexpected ways.

## Lessons Learned and Future Improvements

The main lesson I learned is that a small, complete feature is more valuable than a broad but unfinished platform. Skill Swap could have expanded in many directions, but the prototype became clearer when I focused on the matching process. This made the technical structure easier to manage because I could separate the project into a model for skill data and matching logic, a controller for routes, templates for the screens, and CSS for interface styling.

I also learned that technical decisions shape the user experience directly. The rule-based matching logic made the system fast and explainable, which helped the results page feel more transparent. At the same time, that simplicity limits the richness of the recommendations. If I continued development, I would support multiple offered and wanted skills, allow users to filter by exchange format, and improve the scoring system so it could handle more complex matches.

Another improvement would be to give clearer feedback when a match has already been saved. The current model prevents duplicates, but the interface does not yet tell the user that the match was already in their saved list. A better version could change the button state to “Saved” or display a short confirmation message. This would make the system behaviour more visible and reduce uncertainty.

I would also improve the Match Detail page. At the moment, it shows the profile information and bio, but the most specific match explanation appears most clearly on the Results page. A stronger version would carry the match reason into the detail view, so the user does not lose the recommendation context when opening a specific profile.

Overall, the final prototype achieved the main goal I set during planning: it demonstrates a bespoke matching feature for a Bla+Bla community. Its strongest quality is the focused user flow from skill input to explained match result. Its main limitations are the small dataset, basic scoring logic, and incomplete formal accessibility testing. If I had more time, I would extend the data model, improve saved-state feedback, test with more users, and run more formal performance and accessibility audits. This project helped me understand that web development is not only about making pages work; it is about connecting user needs, data structure, interface clarity, and technical scope into one coherent system.
