---
title: Deploy to Heroku
permalink: /deploy_to_heroku
---

# Deploy to Heroku

## Prereqs:
* have your Angular application created
* have your application pushed to GitHub
* Have a Heroku account [https://www.heroku.com/](https://www.heroku.com/) 

## Heroku setup
* Create a new application
    * you can pick a name or leave it blank for heroku to pick one for you
    * you do not need to add a pipeline
* Once you create the app, it will take you to the `Deploy` tab
    * Select the `GitHub` deployment method and connect your `Heroku` account to your `GitHub` account
      * there will appear another section with a block of text telling you what it will do and a `Connect to Github` button. You will see another window pop up, follow the instructions to connect.
    * Search for your repository to connect and hit the `Connect` button
    * In the next section, click the `Enable Automatic Deploys` button, this will automatically deploy your application each time you push to `GitHub`
    * This has now set up your application to deploy via `Heroku`, now let's get your app configured to be able to deploy.

## Application setup
You need to make a few changes to get your application hosted on `Heroku`: setting up a static express server to serve your application, tell Angular where you want your application built, and tell Heroku how to build your application.

### Setting up your express server

In the terminal in your application directory, run `npm install --save express`. This will add `express` to serve your static Angular application.

Next in VSCode, you want to add a file called `server.js` in the root of your project (next to your `package.json` file), and paste in the folling content:
```
// server.js
const express = require('express');
const app = express();
const path = require('path');

const forceSSL = function() {
  return function (req, res, next) {
    if (req.headers['x-forwarded-proto'] !== 'https') {
      return res.redirect(
       ['https://', req.get('Host'), req.url].join('')
      );
    }
    next();
  }
}
// Instruct the app
// to use the forceSSL
// middleware
app.use(forceSSL());

// Run the app by serving the static files
// in the dist directory
app.use(express.static('dist'));

app.get('/*', function(req, res) {
  res.sendFile(path.join('dist/index.html'));
});

// Start the app by listening on the default
// Heroku port
app.listen(process.env.PORT || 8080);
```

This will set up a server which will use `https` to serve your application from where Angular has built your application.

## Change the `npm start` command

Now we need to make a distinction between how we want to run the application  on your computer (in development mode) vs on Heroku (in production mode).

Update your `package.json` file to have the following changes to your scripts section:
```
  "scripts": {
    "ng": "ng",
    "start": "node server.js",
    "local": "ng serve",
    "build": "ng build",
    "test": "ng test",
    "lint": "ng lint",
    "e2e": "ng e2e",
    "heroku-postbuild": "npm run build"
  },
```

This is doing a few things:
* In order to start you application, instead of running `npm start` you will need to run `npm run local`, this is because `Heroku` will be running `npm start` which is now using your express server, which will not run properly on your computer, since is will forse an `https` connection, and also won't live reload, so you don't want to use that anyway
* It is adding a `heroku-postbuild` step to build your application when you deploy, so that the express server can serve your application

## Setup your Heroku engines

In your `package.json` file, you will need to add a section to tell `Heroku` what engines to use. Add this section under your `"scripts"` section.

```
"engines": {
    "node": "<node version>",
    "npm": "<npm version>"
},
```

In your terminal in your project directory run the following things to fill in the info above:
* run `node --version` and replace`<node version>` above with that output.
* run `npm --version` and replace `<npm version>` above with that ouput.

## Changing Angular's build location

The last thing we need to change is where you application is being built to so the express server can get to it.
In your `angular.json` file, search for `outputPath` and change that from `dist/<your project name>` to just `dist`.

## DEPLOY!

Now that you have made all these changes, you should have the following changed files:
* package.json
* package-lock.json
* angular.json

And one new file
* server.js

Commit and push to `GitHub`, and head back to `Heroku`. On the overview tab, you should see that you have a running build. Once that is done, click on `Open app` to view your application. This will take a few seconds for you application to wake up, but give it time. You should now see your application running.

Happy Coding!

[Home]( /web_group_cohort/project_track )
