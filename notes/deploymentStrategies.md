---
id: k7hra1cir17z8nmhqvr4z6w
title: Deployment strategies
desc: ''
updated: 1683156685114
created: 1675288287027
---

There are lots of different strategies that can be used when deploying applications, its important to figure out the needs of your application before choosing a strategy

Some of the most commons strategies are

## Blue/Green Deployment

Also known as Red/Black Deployment, consists of deploying the new version, testing it, and shifting all the production traffic to the new version once it is stable, erasing the old one

### Pros

* Enforces application quality
* Reduces the presence of bugs
* Reduces the presence of design flaws on the application
* Allows faster and easier rollback

### Cons

* Its expensive because of having both versions running at the same time
* Its slower because of the time it takes for ensuring that the new version is stable

## Canary Deployment

Consists of running both versions at the same time, sending part of the full traffic to the new version and the other to the old version, once the app performance is evaluated, it sends all the remaining traffic to the new version

### Pros

* Allows development team to test the new version's stability
* Allows better performance monitoring
* Faster and better rollback on failures

### Cons 

* Each deployment is very slow
* Increases costs because of running both version at the same time
* Application must be designed for allowing using both versions at the same time

## Ramped Deployment

Also called "Rolling Deployment", consists of gradually replacing instances of the old version of the application for instances of the new version

### Pros

* Provides zero downtime of the application
* Allows performance monitoring

### Cons

* The deployment is slow
* Rollback follows the same process as the deployment making it slow
* The most instances you have, the slower the deployment will be
* Application must be designed for allowing using both versions at the same time

## A/B Deployment

Consists of deploying the new version of a subset of users based on specific conditions in order to evaluate the new version performance and proper operation

### Pros

* Allows performance monitoring and gathering of stadistics
* Allows testing effectiveness of new functions and retrieve feedback from users before publishing the final version

### Cons

* Rollback follows the same process as deployment, making it slow
* The most instances you have, the slower the deployment
* Application must be design for using both versions at the same time
* Users know that they are testing a new version
* How am i going to manage data between versions?

## Shadow Deployment

The new version is deployed on a copy of the infrastructure, receiving the same requests of the old version for evaluating performance

### Pros

* Allows testing the new version real performance
* Allows performing stability tests
* Allows monitoring performance and compare it between versions

### Cons

* Is complex to implement, can cause bad issues if bad implemented
* Its expensive because of having a fuplicate of the infrastructure
* Its difficult to decide when to shut down the old version
* Its difficult to use without affecting data
* How to stop sending reques replicas?
* How do you ensure correct operation?

## Feature toggle

Consists in enabling certain features of the application based on specific flags, like hitting a "switch" for activating or disabling features

### Pros

* You can control which features are going to be activated without switching versions
* Allows the deployment of shared dependencies independently

### Cons

* It requires the coordination of both development and operations teams for implementation
* There will be code that wont be used for big periods of time
* Requires QA team to test the version with all possible flags increasing the workload considerabily

## Recommended practices

* Use pipelines for automating your deployments and implement continous Delivery and Continous Deployment
* Use different clusters for Production and Non-Production enviroments on K8s or OpenShift
* Apply resource limits and alerts oin your resources
* Implement a secrets strategy
* Keep your OS and third-party software update
* Use ephemeral environments and design your app to be stateless
* Have a rollback strategy in case something goes wrong
* Consider your deployment strategy from the applications initial design
