---
id: dipdlpobibs7h9t3cjy8kfk
title: Testing
desc: ''
updated: 1692212912895
created: 1661872329281
---

Contrary to popular believe testing is not a waste of time, testing allows us to deliver better quality applications and take into account changes during development to ensure easy feedback

## Types of testing

En reality there are a lot of different possible tests that can be made, in this notes i will try to explain to the best of my ability the ones i have learned

>Note: remember that the experts recommend to keep unit testing as at least the 70% of the tests done in any software

Lecture Notes
Different types of Testing’s and when they are needed?

### 1. Regression testing

Regression testing is the process of testing changes to Applications to make sure that the existing application still works with the new changes. 

* Automation testing majorly does Regression testing
* Recommended before every release
* Effective Regression Tests can be done by selecting the following test cases –
* Test cases which have frequent defects
* Functionalities Critical
* Integration Test Cases

### 2. Smoke tests

Smoke test development and regression test development are related and similar, The only difference is in depth scope and duration of running the tests

* Typically Runs after every build
* Add the most critical tests to the smoke test suite
* Automate smoke testing in your CD environment

Helps verify the stability of the build

### 3. Component Testing

Component testing is a method where testing of each component in an application is done separately. Component testing may be done in isolation from rest of the system depending on the development life cycle model chosen for that particular application.

Difference between Component Test and Unit Test

### 4. What is Integration Testing?

Integration Testing is defined as a type of testing where software modules are integrated logically and tested as a group.

### 5. System/EndtoEnd Testing:

SYSTEM TESTING is a level of software testing where a complete and integrated software is tested. The purpose of this test is to evaluate the system's compliance with the specified requirements

### 6. Exploratory Testing :

Exploratory testing is an unscripted QA testing technique used to discover unknown issues during and after the software development process. Automation testing has few limits and this exploratory testing is essential to deliver product with bug free confidence

### Difference Between Verification and Validation :

Verification: The process of evaluating work-products (not the actual final product) of a development phase to determine whether they meet the specified requirements for that phase. Its performed before building the product

Validation: The process of evaluating software during or at the end of the development process to determine whether it satisfies specified business requirements. Its performed after building the product

### Other types of testing 

* UAT (User acceptance testing) Testing: This is typically the last step before the product goes live or before the delivery of the product is accepted. UAT is after the product itself is thoroughly tested. Its usually performed by usersor clients
* Load Testing: Load Testing help us to study the behavior of the application under various loads. The main parameter to focus is response time. This study reveals how many concurrent users that server can handle effectively and quickly.
* Stress Testing: Stress Testing help us to observe the stability of the application. The main intention is to identify the breaking point of the server


## Test scenario

Is defined as any functionality that can be tested, its also called Test Condition or Test Possibility.

### How to create a test scenario

1. Carefully study the requirement document, it could be any of the following

    * Business Requirement Specification (BRS)
    * Software Requirement Specification (SRS)
    * Functional Requirement Specification (FRS)

2. Isolate every requirement, and identify what possible user actions need to be tested for it. Figure the technical issues associeted with the requirement, analize and frame possible system abuse scenarios by evaluation the software with a hackers's eye

3. Enumerate test scenarios that cover every possible feature of the software. Ensure these cover every user flow and business flow involved in the operation of the website or app

4. After listing the test scenarios create a Traceability matrix to ensure that every requirement is mapped to a test scenario

5. Get the scenarios reviewed by a supervisor, and then push them to be reviewed by other stakeholders involved in the project

## Functional vs Non-functional requirements

### Functional requirements

Are the main things the client expects from the software, the actual functionality

### Non-functional requirements

Are all other requirements that are not associated with the behaviour like

* Performance
* Scalability
* Usability
* Reliability
* Recoverability
* Security
* Stability



