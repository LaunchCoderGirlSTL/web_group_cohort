---
title: Lesson 300
permalink: /project_300
---

# Lesson 300

## HTTP

### This Lesson's Focus
* Learn how to get data from an external API

### At CoderGirl
* [ABC Lesson 300](https://stackblitz.io/github/AngularBootCamp/dependency-injection-and-http)

In your videos project in _VS Code_
* Delete the JavaScript array of video data from the video dashboard component.
* Use HttpClient to load the video data from `https://api.angularbootcamp.com/videos`:
  * Add HttpClientModule to the imports array in your AppModule
  * Inject HttpClient into your video list component (pass `http: HttpClient` as a parameter to the constructor function)
  * Call the `get` method on the http service to retrieve the video list from the API
  * Call the `subscribe` method and pass a callback function to assign the data to the videos property on the class
  * You will need to remove the date from the template if you added that (the data from the API doesn’t have a date property)
  * Check that the video list shows up in the browser. Look at the network tab to see that the data is coming from the API.

### Do On Your Own 
* Use `ng new` to create a new Angular application for your LaunchCode project (refer to [Lesson 200](https://codergirl.launchcode.org/web_group_cohort/project_200)) (on the command line)
  * Be sure to give it a descriptive project name (not `codergirl-app`) and a 2- or 3-character prefix
* Get routing set up (refer to [Lesson 105](https://codergirl.launchcode.org/web_group_cohort/project_105)) (in _VS Code_)
* Get your homepage set up
* Get a “component works!” message on your page

[Home]( /web_group_cohort/project_track )
