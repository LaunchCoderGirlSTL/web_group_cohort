---
title: Lesson 205
permalink: /project_205
---

# Lesson 205

## Component Inputs

### This Lesson's Focus
* Learn how to share data from a parent component to a child component

### At CoderGirl
* [ABC Lesson 205](https://stackblitz.io/github/AngularBootCamp/component-inputs)

### Workshop:
This will be done in the Video project in _VS Code_

* First, we want to bind move the data into the VideoDashboardComponent and bind it into the VideoListComponent
  * Currently, the list of videos is being obtained by the VideoListComponent (by injecting the VideoLoaderService). We really want the dashboard to obtain the list and bind the data down into the VideoListComponent. 
  * Move the method call to VideoLoaderService to VideoDashboardComponent (instead of VideoListComponent). 
  * Bind the data into the VideoListComponent
  * You will need to add an `@Input` to the VideoListComponent and use the `[videos]=”videoList”` syntax in video-dashboard.component.html. Remember that the part in the square brackets is the Input property on the VideoListComponent, and the part in the quotation marks is the property on the VideoDashboardComponent. You may use other names if you’d like, just make sure they match up.

* Secondly, we want to make each video in the list its own component (instead of just an `li` element)
  * Use the CLI to generate a component that represents a single video in the list (I usually call it a video-list-item)
  * Update your `*ngFor` to use your new component instead of plain HTML (if you follow my example, your component’s selector is `app-video-list-item`)
  * Use component data binding to supply the data for each video entry.
  * Verify that clicking a video still results in visually identifying the selected video.

Homework:
* Get your project deployed to Heroku. Follow instructions here. [Deploying to Heroku](deploy_to_heroku) If you have problems, reach out on slack.
* Add a few more components to your project. Try to flesh out one of the routes/pages. If you need multiple components, think about how you can bind data from a parent to child. 


[Home]( /web_group_cohort/project_track )
