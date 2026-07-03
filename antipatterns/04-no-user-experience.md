# Not connecting your features into a user story

## Example

A spec lists every feature in detail but never describes what a user actually does from start to finish. There's a login flow, a dashboard, a settings page, but no story connecting them.

## Why it's a problem

Features don't equal experience. You can build every item on the list and still ship something confusing. Even if every feature is well described on its own, you must not forget to describe how they connect to each other and how they work together. Without a user journey, the spec describes parts of a car without explaining how to drive it.

[Microsoft's Spec Kit team](https://developer.microsoft.com/blog/spec-driven-development-spec-kit) tells the story of a notification system where the PM, the backend engineer, the frontend developer, and the designer each built a different thing from the same brief. Their diagnosis: "This isn't a failure of communication, it's a failure of shared context." A described journey is that shared context.

## How to fix it

Write at least one end-to-end user journey. "A user opens the app. They see X. They do Y. They get Z." Make it concrete and sequential. It doesn't need to be long. Even a few sentences forces you to think about flow, not just features. [Addy Osmani](https://addyosmani.com/blog/good-spec/) describes the same thing: the spec is "about user journeys, experiences," a map of "the user experience you want to create."
