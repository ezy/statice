---
title: Schedule | React Native app design/build/deploy | twitch.tv
date: 2020-04-14 14:30:55
tags:
  - coding
  - twitch
  - reactjs
---

TLDR;

rebuilding [http://dottyhq.com](https://www.google.com/url?q=https://t.co/1jsyOL1R4X?amp%3D1&sa=D&ust=1586834479074000)

live on [https://twitch.tv/nz_ezy](https://www.google.com/url?q=https://t.co/PWD26XGh1W?amp%3D1&sa=D&ust=1586834479076000)

in PostgreSQL, Express, React, and NodeJS (PERN stack)

_Total build time estimate (4-5 weeks)_

## Work schedule

### Design phase (2 days)

- In Sketch
- React native base sketch template

### React Native build (2-3 weeks)

- Bootstrap project
- Create components
- Routing
- State management (mobx)
- Postman mock API (Mockoon)

### Postgres database (3 days)

- Map current fields
- Migrate new columns and tables from json mocks
- Dockerize

### Express App (1 week)

- Write a swagger file
- Build the express base from swagger
- Currently in SailsJS - convert to Express

### Deployment (2 days)

- Docker to Heroku
- Deploy postgres

## Rough architecture

### Users and roles

- Email
- Name
- Birthdate
- Role - parent, teen, child (no role), admin
- Passwordless (deep link login)
  Some resources
- Remove dots

### Bank

- Add and remove funds
- Monthly/weekly bills / subs

### Notifications

- Opt in
- Teen can operate, interaction get sent to the parent
