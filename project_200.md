---
title: Lesson 200
permalink: /project_200
---

# Lesson 200

## Starting Your Project

### This Lesson's Focus
* How to create a new project locally
* Get set up on Heroku
* Get hooked up to Github

## Before class
1. Install node [https://nodejs.org/en/](https://nodejs.org/en/)
2. Install VSCode [https://code.visualstudio.com/](https://code.visualstudio.com/)

### At CoderGirl
1. VSCode Extensions
    1. TSLint
    1. Angular Language Service
    1. EditorConfig for VS Code
    1. Auto Rename Tag
1. `npm install -g @angular/cli`
1. `ng -v` to make sure the CLI is installed
1. `ng new codergirl-app --prefix cg --routing`
1. `cd codergirl-app`
1. `npm start`
1. Navigate to `http://localhost:4200` in your browser
1. Create a new repo on GitHub and push project (it is already a git repo)
1. Deploy project on Heroku
    1. Get a Heroku account [https://www.heroku.com/](https://www.heroku.com/)
    1. Create a new node project
    1. Hook up to your GitHub project
    1. Deploy

### Notes
`assets/ `
* Your static files

`environments/`
* Your environment configuration, only thing there is a flag for production mode. Open the console to see that it’s running in dev mode, make sure not to ship dev to production (on Heroku, check that it’s not there). Development mode give some extra functionality for checking for errors, and also includes sourcemaps. 

`index.html`
* Notice that there aren’t any script tags in this file--the Angular build process will add the script tags for us. 

`main.ts`
* This is where the application startup code goes. The code in this file is the same as in the StackBlitz apps, but leaves off the StackBlitz-specific lines

`polyfill.ts`
* You may need to uncomment some of the lines depending on what browsers and features you are using

`styles.css`
* Global CSS (works the same way you are used to). The CSS files linked to individual components are scoped to just _that_ component, not all components

`angular.json`
* Configuration for the Angular CLI. You can leave it as is for now. Needed for having multiple angular projects in the same repo or configuring the build process.

`package.json`
* Deps, scripts, project stuff

`README.md`
* Useful stuff to go through when you create a project, but you would replace this later with your information about how to work on your project locally

[Home]( /web_group_cohort/project_track )
