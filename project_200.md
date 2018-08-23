---
title: Lesson 200
permalink: /project_200
---

# Lesson 200

## Starting Your Project

### This Lesson's Focus
* How to create a new project locally
* Get setup on Heroku
* Get hooked up to Github

## Before class
1. Get node [https://nodejs.org/en/](https://nodejs.org/en/)
2. Get VSCode [https://code.visualstudio.com/](https://code.visualstudio.com/)

### At CoderGirl
1. Install VSCode Extensions
    1. TSLint
    2. Angular Language Service
    3. EditorConfig for VS Code
    4. Auto Rename Tag
2. `npm install -g @angular/cli`
3. `ng -v`
4. `ng new codergirl-app —routing`
5. `npm start`
6. Navigate to `http://localhost:4200` in your browser
7. Setup project as git repository
    1. Create a new GitHub Repository **with NO readme**
    1. Follow the instructions for setting up an existing project
8. Get a Heroku account [https://www.heroku.com/](https://www.heroku.com/)
9. Create a new node project
10. Hook up to your GitHub project
11. Deploy

### Notes
`assets/ `
* your static files

`environments/`
* Your environment configuration, only thing there is production mode. Open the console to see that it’s running in dev mode, make sure not to ship dev to production (on Heroku, check that it’s not there).
main.ts
* Same as stackblitz but without the weird stackblitz stuff

`polyfill.ts`
* Only need to change this if you need IE 9-11
styles.css
* Global CSS, component CSS files are just scoped for _that_ component, not all components

`angular.json`
* Configuration for the angular-cli, can leave as is. Needed for having multiple angular projects in the same repo.

`package.json`
* Deps, scripts, project stuff

`README.md`
* Useful stuff to go through when you create a project, but you would replace this later with your readme information for your project

[Home]( /web_group_cohort/project_track )
