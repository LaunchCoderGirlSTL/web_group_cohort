---
title: Lesson SERIAL303
permalink: /project_SERIAL303
---

# Lesson SERIAL303

## Async Pipe

### This Lesson's Focus
* Use a simpler syntax for dealing with observables

### At CoderGirl

* [ABC Lesson SERIAL303](https://stackblitz.io/github/AngularBootCamp/async-pipe) (_StackBlitz_)

### Workshop

* Create a service that uses `HttpClient` to load video data from the API:
    ```
    ng generate service videoData
    ```
* Inject the service into the VideoDashboardComponent and use it to load the
  video data.
* Use the async pipe to unwrap the data in the observable
* Use the RxJS `map` operator in the video data service to transform
  the video data in some way. For example, you could limit the number of
  videos, convert the video names to uppercase, or add a new property to each video object.

### Homework
*In your personal project in VS Code*
* Practice using http
* Generate a service in your project with the CLI
* Inject http into the service
* Do some research on an API that you will use for your project (Google Maps, Openweathermap, etc.)
* Make a method with an http.get call to retrieve some basic data from the API
* Inject the service into your component
* Create a property on your component 
* In the constructor of the component, call the service method and assign the observable to your property
* Use the async pipe in the HTML file to display the data on the screen. You will probably also need the json pipe: 
  <pre>{{myProperty | async | json}}</pre>
* Start laying out your homepage
  * Use the wireframes you designed a couple weeks ago
  * Put some structure on your page


[Home]( /web_group_cohort/project_track )
