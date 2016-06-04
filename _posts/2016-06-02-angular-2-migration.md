---
layout: post
section-type: post
title: angular 2.0 Migration
categories: ['programming']
tags: [ 'angularjs','migration']
---


#### AngularJS Migration to version 2.0 

Angular 2 is amost here, well it is here in theory but not quite production ready.  
Despite that it is near enough to having a production status, we need to start considering the migration path for Angular 1 based Applications.  

Is a complete rewrite the correct approach or it is better to slowly transition to Angular 2?

We need to be mindful of minimising risk and enabling migration whilst maintaining application written in Angular 1.  

First up you will need to prepare code following a style guide - see John Pappa's Angular Style Guide here. [Angular 2 Style Guide](https://github.com/johnpapa/angular-styleguide/blob/master/a2/README.md)  

Next you will need to understand and be prepared for Typescript and ES6, and whilst this is not mandatory it is highly recommended as they will add significant benfit to the ongoing success of next generation Angular apps.  

Finally understanding how to incorperate Angular 2 to current Angular 1 codebase will enable a staged migration path, knowing what to migrate and knowing how to migrate services and components.  

Visual Representation of Angular 1 mapping to Angular 2  

![Migration](/img/angularmigration.png "Angular 1 to Angular 2") 

Some preliminary steps to consider would be:  

From Joe Eames' Pluralsight Course [Preparing for and Migrating Applications to Angular 2](https://app.pluralsight.com/library/courses/migrating-applications-angular-2/table-of-contents)

  1. Follow the style guide  
  2. Update app to latest Angular 1 version - as of this post the latest version is 1.5.6  

  3. New development using components -  As of 1.5 new component functionality is available, shims are available should you be running older versions but wish to use components.   

  4. Switch controllers to components  

  5. Remove incompatible features from directives  

  6. Switch component directives to components  

  7. Implement manual bootstrapping  

  8. Add Typescript and a build  

  9. Start using ES6  

  10. Switch controllers to ES6 classes  

  11. Switch services to ES6 classes  




