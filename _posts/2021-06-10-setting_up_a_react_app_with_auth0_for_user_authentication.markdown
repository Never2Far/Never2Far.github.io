---
layout: post
title:      "Setting up a React APP with Auth0 for User Authentication"
date:       2021-06-10 18:08:50 +0000
permalink:  setting_up_a_react_app_with_auth0_for_user_authentication
---

As I mentioned in my previous post, I am working on converting the JavaScript SPA I made for the JS Portfolio Project to a React APP.

To get started, I used the [create-react-app](https://create-react-app.dev/docs/getting-started) provided by React itself (React was created and is used by Facebook).  From their website:

> "It sets up your development environment so that you can use the latest JavaScript features, provides a nice developer experience, and optimizes your app for production."
> 

Creating a pre-configured app using this tool could not be easier:

```
npx create-react-app resistor-calculator
cd resistor-calculator
npm start
```

With a starting directory structure and everything already set to start coding, my first order of business will be to set up user authentication.  I am doing this first because I want to reference the current user throughout the app and that will be easier with authentication already set up.  In the vanilla JS project, I implemented my own, very basic authentication.  It simply required a username and password and had minimal security (not storing anything sensitive).

While this would be sufficient in the case of the React App, I have since become familiar with using authentication providers such as Auth0.  Auth0 provides an "Auth0 React SDK" and can integrate seamlessly into a React app.  To use Auth0, you must first register on their site and create an application to get the required keys to enter into your React App.

To install Auth0:
```
npm install @auth0/auth0-react
```

A guide for setting up Auth0 with React can be found [here](https://auth0.com/docs/libraries/auth0-react).
Once your account is configured, and Auth0 is installed, it is used by simply wrapping the root-most component of the app with the Auth0 component from the package installed earlier.

Auth0 has a pre-made Universal Login experience, and they have examples of Login/Logout button components in their guide.

My index.js file now looks like this:  

```
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import {Auth0Provider} from '@auth0/auth0-react';

ReactDOM.render(
  <React.StrictMode>
	    <Auth0Provider>
         <App />
			</Auth0Provider>
   </React.StrictMode>,
  document.getElementById('root')
);
```

For more information on React's Strict Mode and why it is helpful, click [here](https://reactjs.org/docs/strict-mode.html).

In my next post I will begin transferring features from the original App and implementing the Auth0 Universal Login page using the Login Button described in their [guide](http://https://auth0.com/docs/libraries/auth0-react).
