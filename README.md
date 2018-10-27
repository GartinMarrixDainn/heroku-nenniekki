# SC-T-303 HUGB - Week 10 Boilerplate Project
Node.js + Express.js app, with support for static files.

## Getting started
### Prerequisites
- [NPM][npm] version 6.4.1+ (could work on older, but not tested).

Optional:

- [Nodemon][nodemon] version 1.18.4+ (could work on older, but not tested).

### Installing
After cloning the repo, run `npm install` in the project directory.

- `git clone https://github.com/arnlaugsson/Week10-boilerplate.git; cd Week10-boilerplate; npm install`

### Running the tests
This repository uses [Jest][jest] testing framework, and [SuperTest][supertest].

To run the tests use `npm test`. Or while developing, keep the tests running on changes `npm run watch` (uses the Jest --watchAll command).

### Running locally
Use `npm start` to start the Express server. The server uses port 5000 by default locally but respects the port number if it is defined by the environment.

While developing it's super nice to have the server restarting on changes, and for that purpose [Nodemon][nodemon] is your friend, run `npm run dev` to start the Nodemon server that will automatically restart the Express server on changes to files.

### Adding Webpack
This is the first objective of this project assignment. Currently, this project is using a single server that is handling both the API and the "client" (which doesn't do much). Ideally, we would want to split this up and have the API running on one port, managed by Node+Express, and the client running on another port, where the client code would be generated by Webpack, on deploy.

1. Refactor the boilerplate code so that the Express app is only responsible for the API and Webpack generates a client that is started on an alternative port serving all other requests.
2. Configure a project to serve both the Webpack dist and the API simultaneously.

### Deployment
This is the second objective of this project assignment, that is for students to get this server deployed.

#### Heroku instructions
1. Install the [Heroku toobelt / CLI][herokucli]
2. Login to Heroku from the shell/command line `heroku login`
3. Create a new "app" on Heroku `heroku create`
4. Push code to app `git push heroku master`

_Note_: Heroku uses a "[Procfile][procfile]" to read how the project should be run. This file is optional in some cases, such as when we use a project that has a package.json file, it will automatically run the "npm start" command. We can, however, change this and set up our own [Procfile][procfile], if we need to customize this.

## Authors
- **Skúli Arnlaugsson** ([@arnlaugsson][arnlaugsson])

## License
This project is licensed under the ISC License - see the [LICENSE.md][license] file for details

[arnlaugsson]: https://github.com/arnlaugsson
[jest]: https://jestjs.io/
[herokucli]: https://devcenter.heroku.com/articles/heroku-cli
[license]: LICENSE.md
[npm]: https://www.npmjs.com/
[nodemon]: https://www.npmjs.com/package/nodemon
[procfile]: https://devcenter.heroku.com/articles/procfile
[supertest]: https://github.com/visionmedia/supertest