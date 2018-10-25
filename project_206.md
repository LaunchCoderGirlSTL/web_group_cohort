---
title: Lesson 206
permalink: /project_206
---

# Lesson 206

## Component Events

### This Lesson's Focus
* Learn how to send messages from a child component to its parent component

### At CoderGirl

* [ABC Lesson 206](https://stackblitz.com/github/AngularBootCamp/component-events) (_StackBlitz_)

### Workshop
This will be done in the Video project in _VS Code_

* Modify your app so that clicking on a video in the list displays the video’s title in the video player
  * Edit your video list component to emit an event when a video is selected. (You will need an @Output property and to call the emit() method)
  * Capture the event on the VideoDashboardComponent. You will need the `()=””` syntax. You will probably want to move the selectedVideo property up to the dashboard.
  * Bind the selectedVideo down into the video player component, and display the selected video's title. 

* **Take this one step at a time**: Make sure you have correctly captured the event in the dashboard (use a `console.log`) before you attempt to bind the selected video into the player. 

[See diagram of how the components should work together](https://docs.google.com/presentation/d/1KSxT0a7eBAw77eSWtgVDAPrMaIDGLPp5VIPKMlTE7FY/edit#slide=id.g448f9c7a23_1_0)

### Homework
* Keep working on your project. Start integrating with your external API if you haven't already done so.

[Home]( /web_group_cohort/project_track )
