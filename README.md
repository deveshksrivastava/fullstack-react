
[![Build Status](https://travis-ci.org/hagopj13/node-express-boilerplate.svg?branch=master)](https://travis-ci.org/hagopj13/node-express-boilerplate)
[![Coverage Status](https://coveralls.io/repos/github/hagopj13/node-express-boilerplate/badge.svg?branch=master)](https://coveralls.io/github/hagopj13/node-express-boilerplate?branch=master)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)

A boilerplate/starter project for quickly building RESTful APIs using Node.js, Express, and Mongoose.

By running a single command, you will get a production-ready Node.js app installed and fully configured on your machine. The app comes with many built-in features, such as authentication using JWT, request validation, unit and integration tests, continuous integration, docker support, API documentation, pagination, etc. For more details, check the features list below.

## Quick Start

To create a project, simply run:

```bash
npx create-nodejs-express-app <project-name>
```

Or

```bash
npm init nodejs-express-app <project-name>
```

## Manual Installation

If you would still prefer to do the installation manually, follow these steps:

Clone the repo:

```bash
git clone --depth 1 https://github.com/hagopj13/node-express-boilerplate.git
cd node-express-boilerplate
npx rimraf ./.git
```

Install the dependencies:

```bash
yarn install
```

Set the environment variables:

```bash
cp .env.example .env

# open .env and modify the environment variables (if needed)
```
## Technologies

The major technologies that were used to build this project are:

- [NodeJS](https://nodejs.org/en/)
- [Typescript](https://www.typescriptlang.org/)
- [TypeORM](https://typeorm.io/)
- [Docker](https://www.docker.com/)

<p align="right">(<a href="#top">back to top</a>)</p>

### Prerequisites

To run this project You will need the following things installed on your machine

- NodeJS
- NPM
- Docker (Optional)


## Table of Contents

- [Features](#features)
- [Commands](#commands)
- [Environment Variables](#environment-variables)
- [Project Structure](#project-structure)
- [API Documentation](#api-documentation)
- [Error Handling](#error-handling)
- [Validation](#validation)
- [Authentication](#authentication)
- [Authorization](#authorization)
- [Logging](#logging)
- [Custom Mongoose Plugins](#custom-mongoose-plugins)
- [Linting](#linting)
- [Contributing](#contributing)


## Features

- **NoSQL database**: [MongoDB](https://www.mongodb.com) object data modeling using [Mongoose](https://mongoosejs.com)
- **Authentication and authorization**: using [passport](http://www.passportjs.org)
- **Validation**: request data validation using [Joi](https://github.com/hapijs/joi)
- **Logging**: using [winston](https://github.com/winstonjs/winston) and [morgan](https://github.com/expressjs/morgan)
- **Testing**: unit and integration tests using [Jest](https://jestjs.io)
- **Error handling**: centralized error handling mechanism
- **API documentation**: with [swagger-jsdoc](https://github.com/Surnet/swagger-jsdoc) and [swagger-ui-express](https://github.com/scottie1984/swagger-ui-express)
- **Process management**: advanced production process management using [PM2](https://pm2.keymetrics.io)
- **Dependency management**: with [Yarn](https://yarnpkg.com)
- **Environment variables**: using [dotenv](https://github.com/motdotla/dotenv) and [cross-env](https://github.com/kentcdodds/cross-env#readme)
- **Security**: set security HTTP headers using [helmet](https://helmetjs.github.io)
- **Santizing**: sanitize request data against xss and query injection
- **CORS**: Cross-Origin Resource-Sharing enabled using [cors](https://github.com/expressjs/cors)
- **Compression**: gzip compression with [compression](https://github.com/expressjs/compression)
- **CI**: continuous integration with [Travis CI](https://travis-ci.org)
- **Docker support**
- **Code coverage**: using [coveralls](https://coveralls.io)
- **Code quality**: with [Codacy](https://www.codacy.com)
- **Git hooks**: with [husky](https://github.com/typicode/husky) and [lint-staged](https://github.com/okonet/lint-staged)
- **Linting**: with [ESLint](https://eslint.org) and [Prettier](https://prettier.io)
- **Editor config**: consistent editor configuration using [EditorConfig](https://editorconfig.org)

<p align="right">(<a href="#top">back to top</a>)</p>

## Commands

Running locally:

```bash
npm dev
```

Running in production:

```bash
npm start
```

Testing:

```bash
# run all tests
npm test

# run all tests in watch mode
npm test:watch

# run test coverage
npm coverage
```

Docker:

```bash
# run docker container in development mode
npm docker:dev

# run docker container in production mode
npm docker:prod

# run all tests in a docker container
npm docker:test
```

Linting:

```bash
# run ESLint
npm lint

# fix ESLint errors
npm lint:fix

# run prettier
npm prettier

# fix prettier errors
npm prettier:fix
```

<p align="right">(<a href="#top">back to top</a>)</p>

## Environment Variables

The environment variables can be found and modified in the `.env` file. They come with these default values:

```bash
# Port number
PORT=3000

# URL of the Mongo DB
MONGODB_URL=mongodb://127.0.0.1:27017/node-boilerplate

# JWT
# JWT secret key
JWT_SECRET=thisisasamplesecret
# Number of minutes after which an access token expires
JWT_ACCESS_EXPIRATION_MINUTES=30
# Number of days after which a refresh token expires
JWT_REFRESH_EXPIRATION_DAYS=30

# SMTP configuration options for the email service
# For testing, you can use a fake SMTP service like Ethereal: https://ethereal.email/create
SMTP_HOST=email-server
SMTP_PORT=587
SMTP_USERNAME=email-server-username
SMTP_PASSWORD=email-server-password
EMAIL_FROM=support@yourapp.com
```

## Project Structure

```
src\
 |--config\         # Environment variables and configuration related things
 |--controllers\    # Route controllers (controller layer)
 |--docs\           # Swagger files
 |--middlewares\    # Custom express middlewares
 |--models\         # Mongoose models (data layer)
 |--routes\         # Routes
 |--services\       # Business logic (service layer)
 |--utils\          # Utility classes and functions
 |--validations\    # Request data validation schemas
 |--app.js          # Express app
 |--index.js        # App entry point
```
## Project Structure (how to add files)

If you want to add a new route then you will goto `/routes` folder and add a new Router.
Then register that router in the `index.ts` file under the `/routes` folder.

Then you will create a Controller under the `/controllers` directory.All business logics should go into there.

Specific use cases should be handles by Service classes under the `/service` folder.

All Database related things should go under `/repositories` folder.

To create a new model for data base look into the `/models` folder.

<p align="right">(<a href="#top">back to top</a>)</p>

#### Version in Node.js
 ## why we should use it
    - Fix Bugs - breaking changing like adding new feilds, change from json to xml, required feild, remove property
    - Deprivciate old feature - hit 404 page
    - New feature for new users 

 MAJOR.MINOR.PATCH - 
    Semantic versionning 
        - PATCH - change form 1.2.0 to 1.2.1 
            - bug fix, performace improvemnet, enviorment or internal tweaks - consumer can change as no change in request, responce or body. Cunsumer is suggent to upgrade the changes.
        - MINOR - change form 1.2.0 to 1.3.1
            - New feature, exitnig end point depricate, example we have retrive/create/update products, mincon chaneg is adding delete and req by id
            - Always backword compatabe, cusumer can upgrade freely
            - Nothing will break
        - MAJOR - change form 1.2.0 to 2.0.0
            - Major update are non-compatable consurems cannot upgrade without changing there software application
            - change end point or signature - /api/porduct to /api/user/products
            - Remove the end point
 - URI version
    - GET /api/v1/getusers
    - GET /api/v2/getusers
     - pros- easy to implement and ungerstand, clear sepratino of api version in the url
     - Cons
        - can lead to cluttering url and harder to read endpoints
        - not good for rest archeture and uri should represnt the resource, not the version
 - Query Parameter version 
   Change by query, main query don't change only the parameters changes
    - /api/getusers?Version=1
    - /api/getusers?Version=2
    - Props - clear sepration of API version with out changing the URL, easy to implment 
    - Cons - not as understandable as uri versioning
 - Custome Header 
    Version are included in the http headers of the api request 
    -  GET /api/users headers:{'x-api-versino':'1'}
    -  GET /api/users headers:{'x-api-versino':'2'}
    - Props - Adher to REST PRINCIPLES, 
    - Cons - NOT GOOD LIKE OTHERS, REQUIRE EFFORT TO SEE AS VERSION ARE HIDDEND IN HEADER
 - Content negotiation versioning 
    - Content negotiation is a powerful technique used in RESTful APIs to manage versioning without cluttering the URL.
    - Accept: application/vnd.myapi.v1+json
    - Props - Clean URLs,without breaking existing clients , Decoupling the resource identity from its representation

 #### Summary 
    - URL path versioning is widely adopted due to its simplicity and clarity, making it a strong choice for many APIs. However, if you require more flexibility and want to keep your URLs clean, header versioning or content negotiation may be more suitable.
<p align="right">(<a href="#top">back to top</a>)</p>
   
## Feature 
 - winston & morgan 
 - error handling + global page handling + Logging
 - 404 page
 
 ### links for error page
 - http://localhost:5001/error (error page)
 - http://localhost:5001/api/v1/resource (global error page)
 - http://localhost:5001/api/v1/resource34534 (not used)


 ### Inpratinon Github repo (Middleware)
 - [Express Typscript docker](https://github.com/iamsohel/express-typescript-boilerplate-docker/blob/main/README.md#top)
     -  This repository focuses on TypeScript and is production-ready, including:
    -  TypeORM for database management
    -  Swagger for API documentation
    -  Docker support for containerized deployments
    -  Prettier, ESLint, and Husky for code quality
    -  Dependency injection for better modularity.

 - [Node Express boiler plate](https://github.com/hagopj13/node-express-boilerplate/blob/master/README.md?plain=1)
    - This popular boilerplate is designed for building RESTful APIs in production with features like:
    -  Advanced logging (Winston, Morgan)
    -  Centralized error handling
    -  API documentation using Swagger
    -  Testing with Jest
    -  Docker support and CI integration (Travis CI)
    -  Security enhancements (Helmet, XSS sanitization, CORS)
    -  Pre-configured for MongoDB using Mongoose.
    -  It's a great choice for scalable and well-structured applications.

 - [TypeScript-Node-Starter-Microsoft](https://github.com/microsoft/TypeScript-Node-Starter)
    - This project offers a robust starting point for TypeScript-based applications, featuring:

    - Best practices for TypeScript and Express.js
    - Linting, formatting, and a detailed folder structure
    - Configurations for modern Node.js development.


 - [MEAN Stack Starter](https://github.com/linnovate/mean   )
   - While this is a full-stack repository (MongoDB, Express, Angular, Node.js), it offers a strong backend configuration for Express. It's ideal for those looking to pair Express with front-end frameworks.
 - router level - router.get('/users/:id', logger, loggerPrint, deleteUser); with next
 - global level - app.use(cors()); - execute in order
 - Error handling - https://github.com/Not-Jukkapan/ecommerce-backend
 - Express - https://expressjs.com/en/5x/api.html#express
 - (nodejs-typescript-express-typeorm-mysql-boilerplate)[https://github.com/vinodnextcoder/nodejs-typescript-express-typeorm-mysql-boilerplate/]
 - https://www.youtube.com/watch?v=YuhKhkQqtP8
 - (middleware)[https://www.youtube.com/watch?v=J9Y7-S7POe4&t=1515s]
 - https://github.com/hagopj13/node-express-boilerplate/blob/master/src/routes/v1/user.route.js

<p align="right">(<a href="#top">back to top</a>)</p>
 ##### Status code error

 ```
 npm install http-status-codes --save
 ```

 ```
import {
	ReasonPhrases,
	StatusCodes,
	getReasonPhrase,
	getStatusCode,
} from 'http-status-codes';

response
	.status(StatusCodes.OK)
	.send(ReasonPhrases.OK);

response
	.status(StatusCodes.INTERNAL_SERVER_ERROR)
	.send({
		error: getReasonPhrase(StatusCodes.INTERNAL_SERVER_ERROR)
	});

response
	.status(getStatusCode('Internal Server Error'))
	.send({
		error: 'Internal Server Error'
	});
 ```

## API Documentation

To view the list of available APIs and their specifications, run the server and go to `http://localhost:3000/v1/docs` in your browser. This documentation page is automatically generated using the [swagger](https://swagger.io/) definitions written as comments in the route files.

### API Endpoints

List of available routes:

**Auth routes**:\
`POST /v1/auth/register` - register\
`POST /v1/auth/login` - login\
`POST /v1/auth/refresh-tokens` - refresh auth tokens\
`POST /v1/auth/forgot-password` - send reset password email\
`POST /v1/auth/reset-password` - reset password\
`POST /v1/auth/send-verification-email` - send verification email\
`POST /v1/auth/verify-email` - verify email

**User routes**:\
`POST /v1/users` - create a user\
`GET /v1/users` - get all users\
`GET /v1/users/:userId` - get user\
`PATCH /v1/users/:userId` - update user\
`DELETE /v1/users/:userId` - delete user

<p align="right">(<a href="#top">back to top</a>)</p>
## Error Handling

The app has a centralized error handling mechanism.

Controllers should try to catch the errors and forward them to the error handling middleware (by calling `next(error)`). For convenience, you can also wrap the controller inside the catchAsync utility wrapper, which forwards the error.

```javascript
const catchAsync = require('../utils/catchAsync');

const controller = catchAsync(async (req, res) => {
  // this error will be forwarded to the error handling middleware
  throw new Error('Something wrong happened');
});
```

The error handling middleware sends an error response, which has the following format:

```json
{
  "code": 404,
  "message": "Not found"
}
```

When running in development mode, the error response also contains the error stack.

The app has a utility ApiError class to which you can attach a response code and a message, and then throw it from anywhere (catchAsync will catch it).

For example, if you are trying to get a user from the DB who is not found, and you want to send a 404 error, the code should look something like:

```javascript
const httpStatus = require('http-status');
const ApiError = require('../utils/ApiError');
const User = require('../models/User');

const getUser = async (userId) => {
  const user = await User.findById(userId);
  if (!user) {
    throw new ApiError(httpStatus.NOT_FOUND, 'User not found');
  }
};
```
<p align="right">(<a href="#top">back to top</a>)</p>
## Validation

Request data is validated using [Joi](https://joi.dev/). Check the [documentation](https://joi.dev/api/) for more details on how to write Joi validation schemas.

The validation schemas are defined in the `src/validations` directory and are used in the routes by providing them as parameters to the `validate` middleware.

```javascript
const express = require('express');
const validate = require('../../middlewares/validate');
const userValidation = require('../../validations/user.validation');
const userController = require('../../controllers/user.controller');

const router = express.Router();

router.post('/users', validate(userValidation.createUser), userController.createUser);
```

## Authentication

To require authentication for certain routes, you can use the `auth` middleware.

```javascript
const express = require('express');
const auth = require('../../middlewares/auth');
const userController = require('../../controllers/user.controller');

const router = express.Router();

router.post('/users', auth(), userController.createUser);
```

These routes require a valid JWT access token in the Authorization request header using the Bearer schema. If the request does not contain a valid access token, an Unauthorized (401) error is thrown.

**Generating Access Tokens**:

An access token can be generated by making a successful call to the register (`POST /v1/auth/register`) or login (`POST /v1/auth/login`) endpoints. The response of these endpoints also contains refresh tokens (explained below).

An access token is valid for 30 minutes. You can modify this expiration time by changing the `JWT_ACCESS_EXPIRATION_MINUTES` environment variable in the .env file.

**Refreshing Access Tokens**:

After the access token expires, a new access token can be generated, by making a call to the refresh token endpoint (`POST /v1/auth/refresh-tokens`) and sending along a valid refresh token in the request body. This call returns a new access token and a new refresh token.

A refresh token is valid for 30 days. You can modify this expiration time by changing the `JWT_REFRESH_EXPIRATION_DAYS` environment variable in the .env file.

## Authorization

The `auth` middleware can also be used to require certain rights/permissions to access a route.

```javascript
const express = require('express');
const auth = require('../../middlewares/auth');
const userController = require('../../controllers/user.controller');

const router = express.Router();

router.post('/users', auth('manageUsers'), userController.createUser);
```

In the example above, an authenticated user can access this route only if that user has the `manageUsers` permission.

The permissions are role-based. You can view the permissions/rights of each role in the `src/config/roles.js` file.

If the user making the request does not have the required permissions to access this route, a Forbidden (403) error is thrown.

<p align="right">(<a href="#top">back to top</a>)</p>

## Logging

Import the logger from `src/config/logger.js`. It is using the [Winston](https://github.com/winstonjs/winston) logging library.

Logging should be done according to the following severity levels (ascending order from most important to least important):

```javascript
const logger = require('<path to src>/config/logger');

logger.error('message'); // level 0
logger.warn('message'); // level 1
logger.info('message'); // level 2
logger.http('message'); // level 3
logger.verbose('message'); // level 4
logger.debug('message'); // level 5
```

In development mode, log messages of all severity levels will be printed to the console.

In production mode, only `info`, `warn`, and `error` logs will be printed to the console.\
It is up to the server (or process manager) to actually read them from the console and store them in log files.\
This app uses pm2 in production mode, which is already configured to store the logs in log files.

Note: API request information (request url, response code, timestamp, etc.) are also automatically logged (using [morgan](https://github.com/expressjs/morgan)).

## Custom Mongoose Plugins

The app also contains 2 custom mongoose plugins that you can attach to any mongoose model schema. You can find the plugins in `src/models/plugins`.

```javascript
const mongoose = require('mongoose');
const { toJSON, paginate } = require('./plugins');

const userSchema = mongoose.Schema(
  {
    /* schema definition here */
  },
  { timestamps: true }
);

userSchema.plugin(toJSON);
userSchema.plugin(paginate);

const User = mongoose.model('User', userSchema);
```
<p align="right">(<a href="#top">back to top</a>)</p>
### toJSON

The toJSON plugin applies the following changes in the toJSON transform call:

- removes \_\_v, createdAt, updatedAt, and any schema path that has private: true
- replaces \_id with id

### paginate

The paginate plugin adds the `paginate` static method to the mongoose schema.

Adding this plugin to the `User` model schema will allow you to do the following:

```javascript
const queryUsers = async (filter, options) => {
  const users = await User.paginate(filter, options);
  return users;
};
```

The `filter` param is a regular mongo filter.

The `options` param can have the following (optional) fields:

```javascript
const options = {
  sortBy: 'name:desc', // sort order
  limit: 5, // maximum results per page
  page: 2, // page number
};
```

The plugin also supports sorting by multiple criteria (separated by a comma): `sortBy: name:desc,role:asc`

The `paginate` method returns a Promise, which fulfills with an object having the following properties:

```json
{
  "results": [],
  "page": 2,
  "limit": 5,
  "totalPages": 10,
  "totalResults": 48
}
```

## Linting

Linting is done using [ESLint](https://eslint.org/) and [Prettier](https://prettier.io).

In this app, ESLint is configured to follow the [Airbnb JavaScript style guide](https://github.com/airbnb/javascript/tree/master/packages/eslint-config-airbnb-base) with some modifications. It also extends [eslint-config-prettier](https://github.com/prettier/eslint-config-prettier) to turn off all rules that are unnecessary or might conflict with Prettier.

To modify the ESLint configuration, update the `.eslintrc.json` file. To modify the Prettier configuration, update the `.prettierrc.json` file.

To prevent a certain file or directory from being linted, add it to `.eslintignore` and `.prettierignore`.

To maintain a consistent coding style across different IDEs, the project contains `.editorconfig`

## Contributing

Contributions are more than welcome! Please check out the [contributing guide](CONTRIBUTING.md).

## Inspirations

- [danielfsousa/express-rest-es2017-boilerplate](https://github.com/danielfsousa/express-rest-es2017-boilerplate)
- [madhums/node-express-mongoose](https://github.com/madhums/node-express-mongoose)
- [kunalkapadia/express-mongoose-es6-rest-api](https://github.com/kunalkapadia/express-mongoose-es6-rest-api)

## License
<p align="right">(<a href="#top">back to top</a>)</p>

[MIT](LICENSE)