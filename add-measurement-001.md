# Add Measurement

Date: 20220904

## Status
* assept.

## Context and Problem Statement

* If don't have data to prove result, The all of feature request only could keep in imaginary,
so this adr will help build data collect mechanism,
And after it, we could use it to estimate features, and reference it, we will go or no go. 

* Exists Measurement:
   * "react-ga" only in client app, and only for logging page-view.

## Considered Options
* Google analytics
   * use google analytics, we could reuse google infrastructure,
     and focus on how to collect data.
     when google gets the data, it will do de-identification, this will let us not eaily mapping with real users.
* Build our own data analytics platform.
   * if build our own data platform, we need operate our machine,
     but we could have all the control with our data.

* Build own cdp solution.
   * [matomo](matomo.org)
   * [shynet](https://github.com/milesmcc/shynet)

* App error tracing
   * [sentry](https://sentry.io/)
   * [newrelic](https://newrelic.com/)

## Decision Outcome

### How to make it happen and intermediate milestones
1. add Measurement to client side (user with browser)
2. add Measurement to the application layer. (backend)
   * When adding it with the application layer, we could trace which backend is most used, and we could improve that backend.

### Positive Consequences
* It could help us use data to drive decisions. 
### Negative Consequences
* Need to extract traffic to logging data, and could use async ways to improve it. 
