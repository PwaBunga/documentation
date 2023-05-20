* [Documentation homepage](https://github.com/PwaBunga/documentation/)
* [Documentation of the PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/STARTER.md)
* [Documentation of the PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/CSS.md)
* [Documentation of the PWA Bunga! PWA](https://github.com/PwaBunga/documentation/blob/main/PWA.md)

<div align="center">
  <img src="https://pwabunga.com/github/logo-pwabunga-circle.png" alt="logo PWA Bunga!"/>
</div>

[French version](https://github.com/PwaBunga/documentation/tree/main/fr)

# Welcome to the PWA Bunga! documentation

Welcome to the PWA Bunga! project, a modern, modular front-end template for fast and efficient development of websites and Progressive Web Apps

This documentation explains how to use the files provided in the PWA Bunga! project to create performant and user-friendly progressive web applications. It also provides information on best practices for customizing the files to fit the specific needs of your application and how to integrate them to create a complete progressive web application.

Whether you're a beginner or an experienced developer, this front-end template will help you save time and focus on creating specific features for your site or application, rather than setting up the basic architecture.

* The project's website: **[pwabunga.com](https://pwabunga.com/)**
* The project's documentation (on project'swebsite): **[pwabunga.com/documentation/](https://pwabunga.com/documentation/)**
* The project's demo: **[demo.pwabunga.com](https://demo.pwabunga.com/)**

&nbsp;

## Contents of PWA Bunga!

This front-end template is designed in a modular way and consists of three main modules: Starter, CSS, and PWA.

### PWA Bunga! Starter

The Starter module provides the basic files and folders to quickly start a website or PWA project. This includes resource folders, an HTML template, 404 and 403 error pages, an htaccess file, favicons in .ico, .svg or .png formats, as well as empty CSS and JS files that can be filled according to your needs.

* [Documentation of the PWA Bunga! Starter](https://github.com/PwaBunga/documentation/blob/main/STARTER.md)

### PWA Bunga! CSS

The CSS module includes a base CSS file with best practices, HTML element normalization, ergonomic improvements, and reset to improve consistency and compatibility across browsers, as well as to make the developer's work easier.

* [Documentation of the PWA Bunga! CSS](https://github.com/PwaBunga/documentation/blob/main/CSS.md)

### PWA Bunga! PWA

The PWA module provides files and instructions to transform your website into a Progressive Web App (PWA). This includes the webmanifest file that contains application metadata, icons for the home screen, the service worker file that allows the application to work offline, a JavaScript file to enhance the user experience, and an optional CSS file to customize the user interface.

#### [Webmanifest](https://github.com/PwaBunga/documentation/blob/main/pwa/WEBMANIFEST.md)

* [General PWA Information](https://github.com/PwaBunga/documentation/blob/main/pwa/WEBMANIFEST.md#general-information-about-the-pwa)
* [Navigating the PWA](https://github.com/PwaBunga/documentation/blob/main/pwa/WEBMANIFEST.md#navigating-the-pwa)
* [PWA Theme](https://github.com/PwaBunga/documentation/blob/main/pwa/WEBMANIFEST.md#pwa-theme)

#### [Icons](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONS.md)

* [Icons and Touch icons for application environments and older versions of Android](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#icons-and-touch-icons-for-application-environments-and-older-versions-of-android)
  - [Icon display](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#icon-display)
  - [Icon dimensions](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#icon-dimensions)
  - [Call icons](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#call-icons)
* [Maskable icons: adaptive icons for the Android environment](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#maskable-icons-adaptive-icons-for-the-android-environment)
  - [Safe area and adaptive icon shapes](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#safe-area-and-adaptive-icon-shapes)
  - [Display of adaptive icons](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#display-of-adaptive-icons)
  - [Call for adaptive icons](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#call-for-adaptive-icons)
* [Touch icon for iOS environment](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#touch-icon-for-ios-environment)
  - [Formats and dimensions of apple-touch-icon.png](https://github.com/PwaBunga/documentation/blob/main/pwa/ICONES.md#formats-and-dimensions-of-apple-touch-iconpng)

#### [Service worker](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md)

* [Configuring cache and request processing](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#configuring-cache-and-request-processing)
  - [Cache name and version](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#cache-name-and-version)
  - [Cached Resources](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#cached-resources)
  - [Choice of request processing strategy](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#choice-of-request-processing-strategy)
  - [Declaration of a dynamic folder](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#declaration-of-a-dynamic-folder)
* [Cache manipulation](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#cache-manipulation)
  - [Add resources to cache](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#add-resources-to-cache)
  - [Update cache resources](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#update-cache-resources)
  - [Deleting a cache instance](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#deleting-a-cache-instance)
  - [Removing older versions from cache](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#removing-older-versions-from-cache)
* [Query Processing Strategies](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#query-processing-strategies)
  - [Cache only](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#cache-only)
  - [Network only](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#network-only)
  - [Cache first](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#cache-first)
  - [Network first](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#network-first)
  - [Stale While Revalidate](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#stale-while-revalidate)
* [Service worker events](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#service-worker-events)
  - [Install event](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#install-event)
  - [Activate event](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#activate-event)
  - [Message event](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#message-event)
  - [Fetch event](https://github.com/PwaBunga/documentation/blob/main/pwa/SERVICEWORKER.md#fetch-event)

#### pwabunga.js

* Service worker registration
  - pwaRegister function
* Improved user experience
  - pwaInstall function
  - pwaUpdate function
  - pwaShare function
  - pwaParams function
* Permissions
  - pwaNotification function
  - pwaGeolocation function

#### pwabunga-ui.css



&nbsp;

## Getting started with PWA Bunga!

### Old school way

* Download the PWA Bunga! front-end template zip: [Download PWA Bunga! 1.0](https://pwabunga.com/assets/download/pwabunga-v1-0.zip)
* Open your favorite code editor
* Customize the template to fit your project!

&nbsp;

## Follow the PWA Bunga! project

### Source code

PWA Bunga! is a project maintained on Github.

#### Github account of PWA Bunga!

* [https://github.com/PwaBunga](https://github.com/PwaBunga)

#### PWA Bunga!'s main repository

* [https://github.com/PwaBunga/template](https://github.com/PwaBunga/template)

#### PWA Bunga!'s documentation repository

* [https://github.com/PwaBunga/documentation](https://github.com/PwaBunga/documentation)

#### PWA Bunga! modules repositories

These 3 repositories correspond to the 3 modules of PWA Bunga!, they are present to facilitate and organize contributions to the project.

* [https://github.com/PwaBunga/starter](https://github.com/PwaBunga/starter)
* [https://github.com/PwaBunga/css](https://github.com/PwaBunga/css)
* [https://github.com/PwaBunga/pwa](https://github.com/PwaBunga/pwa)

### What's New

To stay informed about the latest updates and news, you can follow the project's Twitter account:

* [https://twitter.com/pwabunga](https://twitter.com/pwabunga)

### Discussing the project

Feel free to use the discussions module in the main repository to give your opinion, thoughts or ideas about PWA Bunga!

* [https://github.com/PwaBunga/template/discussions](https://github.com/PwaBunga/template/discussions)

&nbsp;

## Contribute

To contribute, you can use the issue trackers of the PWA Bunga! module repositories.

* [https://github.com/PwaBunga/starter/issues](https://github.com/PwaBunga/starter/issues)
* [https://github.com/PwaBunga/css/issues](https://github.com/PwaBunga/css/issues)
* [https://github.com/PwaBunga/pwa/issues](https://github.com/PwaBunga/pwa/issues)

Changes made to these 3 repositories will then be applied to the main project repository.

The issue tracker is the preferred channel for bug reports, features requests and submitting pull requests, but please respect the following restrictions:

* Please **do not** use the issue tracker for personal support requests.
* Please **do not** derail or troll issues. Keep the discussion on topic and= respect the opinions of others.

&nbsp;
