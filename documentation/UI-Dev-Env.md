---
layout: plain
title: UI Development Environment
description: >
  How to setup-up a Polypheny-UI development environment.
hide_description: true
---

This guideline describes how to setup-up a development environment for the [Polypheny-UI](https://github.com/polypheny/Polypheny-UI). In the following, we describe two approaches.

First, make sure you have [node.js](https://nodejs.org/en/) installed. Then, clone [Polypheny-UI](https://github.com/polypheny/Polypheny-UI), open the root folder and run

```
npm install
```

If you haven't installed Angular yet, do so by executing

```
npm install -g @angular/cli
```

Now you can run
```
ng serve --aot -o
```

You should now be able to open the UI in your browser by entering the url [http://localhost:4200/](http://localhost:4200/). Please make sure you have a running instance of Polypheny-DB.



## Using gradle
If you want to build the project without having to install NodeJS and Angular, you can do so by executing

```
./gradlew npm_install
```

The Angular Live Development Server can be started using

```
./gradlew npm_start
```

You should now be able to open the UI in your browser by entering the url [http://localhost:4200/](http://localhost:4200/). Please make sure you have a running instance of Polypheny-DB.

## Testing
Polypheny-UI is tested with cypress framework.\
With Cypress, tests are performing assertions using a real browser, the same way a real user would use the software.

Cypress tests can be ran

- using the Cypress test runner (development mode)
- using a command line (CI/CD mode)


### Cypress project Structure
Tests are located in ```cypress/integration/``` folder.
- ```/fixtures``` are used to store and manage test data
- ```/integration``` contains the tests
- ```/plugins``` contain custom plugins if needed.
- ```/screenshots``` and ```/videos``` contain the recording of the tests, Git ignored
- ```/support``` is a custom library of assertion and common user actions or page objects, to avoid code
duplication in the tests themselves.

### Setting up backend
Cypress assumes that both Polypheny-UI and Polypheny-DB are up and running in test mode.

To run Polypheny-DB in test mode Pass ```-testMode``` parameter in run configuration of your IDE.

Some tests require creating schema and tables. Queries for such cases should be added in 
```test-helper/src/main/java/org/polypheny/ui/test/TestHelper.java```.\
 Also ```TestHelper.java``` needs to be executed after running Polypheny-DB and before running Cypress so that the required tables or schema can be created.

### Cypress can be started using
    npx Cypress open
Once the test runner is up, you can choose to run one or several tests by selecting them from the interface.
Click on one of them and the test will start.

### To add a test
- Add a test.spec.ts into the cypress/integration folder.
- The test is instantly available in the list
- Click on the test
- Start to add some code

#### For executing queries for SQL tests in Cypress you can use the following command replacing the ````"query"```` with the   query you want to execute
    cy.window().invoke("executeQuery", "query");





