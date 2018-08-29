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
    * You should have one real route called `dashboard`. If the user tries to go to the "empty route"(i.e. `path: ''`), they should be redirected to "/dashboard." 
    * The dashboard module should load the DashboardComponent for its empty route.
    * Refer to lesson 105 and the StackBlitz homework for a reminder how to do this. Make sure the magic string in app-routing.module.ts is formed properly.
    * Clean up the `app.component.html` so it is just showing your router outlet.
* Use an instance of each of the other three components inside your `video-dashboard.component.html`



[Home]( /web_group_cohort/project_track )
