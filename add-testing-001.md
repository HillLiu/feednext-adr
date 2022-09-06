# Add Testing

Date: 20220904

## Status
* assept.

## Context and Problem Statement

Some people will thinking coding with test (Unit Test), will let it become slow,
But when you need process large changes or any basic feature changes,
it could help you quickly verify if all existing features are still correct.
And it also makes you more confident to do refactoring.

## Considered Options

### Test Runner 
* [mocha](https://mochajs.org/)
* [node 18 build in test runner](https://nodejs.org/api/test.html)

### React unit test framework
* [React test](https://reactjs.org/docs/testing.html) 
   * [Jest](https://jestjs.io/)
   * [@testing-library/react](https://testing-library.com/docs/react-testing-library/intro/)

### unit test code coverage
* [nyc](https://www.npmjs.com/package/nyc)

### End to end test
* [Cypress](https://www.cypress.io/) 
* [Puppeteer](https://developer.chrome.com/docs/puppeteer/)

## Decision Outcome

### How to make it happen and intermediate milestones
* In this step, we'll follow "Add Measurement", and learn to know which page is important.
* We will promote high usage page's code coverage.
* Choose solution
   * Test Runner -> mocha
      * mocha could use most of node version
   * React unit test framework -> @testing-library/react
      * testing-library could integrate with more library.
   * End to end test -> Cypress
     * It's easy to install.

### Positive Consequences
* We could more confident to make change,
and could use the command line to do testing to avoid new changes breaking your existing code.
 
### Negative Consequences
* Need extra time to develop testing code.
