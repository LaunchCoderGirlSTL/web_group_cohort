---
title: Lesson 201
permalink: /project_201
---

# Lesson 201

## Component Heirarchy

### This Lesson's Focus
* Create components and setup routing

### At CoderGirl
* [ABC Lesson 201](https://stackblitz.io/github/AngularBootCamp/component-hierarchy)

### Do On Your Own

In your codergirl-app:
* Create a new module
    * `ng generate module dashboard —routing`
* Create four components inside the dashboard module
    * `ng generate component dashboard/videoDashboard`
    * `ng generate component dashboard/videoList`
    * `ng generate component dashboard/videoPlayer`
    * `ng generate component dashboard/statFilters`
* Setup routing
    * Your `video-dashboard` component should be the root of your application. Refer to lesson 105 for a reminder how to do this. Make sure the magic string is working properly.
    * Clean up the `app.component.html` so it is just showing your routing component
* Add each of the components inside your `video-dashboard.component.html` like in the stackblitz example


[Home]( /web_group_cohort/project_track )
