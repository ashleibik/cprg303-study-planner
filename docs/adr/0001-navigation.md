# **App Navigation ADR**

## Status

**Accepted**

This proposition has been discussed, reviewed and approved by all team members.

## Context

Because the chosen app is a Study Planner, users need a way to easily view and switch to different areas of the app. The different screens may involve components such as:

- Managing student tasks
- Calendar viewing
- Modifying preferences and app settings
- Monitoring student progress

## Decision

In order to build Schedinuity’s tab bar and allow for seamless navigation operation, Expo Router will be utilized as the structure of Schedinuity’s navigation. Expo Router will be used to structure the app’s designated pages based on the files in the app folder so that the project is easy to maintain. Expo Router will also work with React Native to deliver this. Potential pages include:

- Student Dashboard
- Tasks
- Calendar and Due Dates
- Progress
- Schedule Builder
- Settings

## Consequences

Pros:

Utilizing Expo Router with React Native will allow for a simple way to deliver the output of our project. The delivery can be completed via Android and iOS and there are not many extra steps to take in order to initiate a new section of the app.

Cons:

Expo Router is a relatively new system for all team members which can lead to some naming errors, route issues and confusion with the app layout.
 
