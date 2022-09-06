# Simplify Environment

Date: 20220903

## Status
* assept.

## Context and Problem Statement

Although current setup step not too complicate,
but it is a hidden cost, when projects become bigger, the same code config needs duplication to two different places.

The docker-compose not execute as a original simple way, we should make it back to one file when it not become too complicated,
It's a one time job but could benefit all new developers to start this project with zero config and start it only needing to run `docker-compose up`.

## Considered Options
* [ ] initialize mongodb with /docker-entrypoint-initdb.d
   * let it easy use docker-compose down to reset db.
   * https://stackoverflow.com/questions/42912755/how-to-create-a-db-for-mongodb-container-on-start-up
* [ ] sync docker-compose.yml and use .env.dev and .env.prod to separate environment
* [ ] disable a service in docker-compose.yml for different environment
   * https://rotadev.com/is-there-any-way-to-disable-a-service-in-docker-compose-yml-dev/

## Decision Outcome

### How to make it happen and intermediate milestones
This task will estimate 8 day to finish, and already have a task to do.

### Positive Consequences
* It helps the new user setup environment easily. 

### Negative Consequences
* Need extra effort to design different dimensions(such as dev or production) mechanism.
