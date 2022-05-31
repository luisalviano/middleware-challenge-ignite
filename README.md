<h1 align="center">🚀 Challenge #2 - Working with Middlewares 🚀</h1>

This is the second challenge from [Rocketseat's Ignite](https://www.rocketseat.com.br/ignite) Node.js bootcamp. The objective of this challenge is to practice working with middlewares.

<p align="center">
  <a href="#about-the-application">About</a> •
  <a href="#technologies">Technologies</a> •
  <a href="#getting-started">Getting Started</a> •
  <a href="#middlewares">Middlewares</a> •
  <a href="#running-the-tests">Tests<a>
</p>

<p id="insomnia" align="center">
  <a href="https://insomnia.rest/run/?label=ToDo%20App&uri=https%3A%2F%2Fgithub.com%2Fmarialuizams%2Fmiddleware-challenge-ignite%2Fblob%2Fmain%2Finsomnia.json" target="_blank"><img src="https://insomnia.rest/images/run.svg" alt="Run in Insomnia"></a>
</p>

## About the application

In this challenge, I'll be making a few changes on the <a href="https://github.com/marialuizams/todo-challenge-nodejs">ToDo app</a>. Just like the previous task manager application, it must be possible to create an user, as well as the <i>todos</i> (tasks) CRUD:

- Create a new <i>todo</i>;
- List all <i>todos</i>;
- Update `title` and `deadline` of an existing <i>todo</i>;
- Check a <i>todo</i> as done;
- Delete a <i>todo</i>.

In addition, the application will have a free plan where the user can only create up to ten <i>todos</i>, and a Pro plan that allows the user to create ilimited <i>todos</i>. This should be implemented using middlewares.

## Technologies

- [Node.js](https://nodejs.org/en/)
- [Express](http://expressjs.com/)
- [Jest](https://jestjs.io/)

## Getting Started

Clone this repository and access the folder:
```
$ git clone https://github.com/marialuizams/middleware-challenge-ignite
$ cd middleware-challenge-ignite
```
Install dependencies using:
```
$ yarn
# or
$ npm install
```

Start the app by running:
```
$ yarn dev
```
The application should start running on http://localhost:3333.

Import the `insomnia.json` file on the Insomnia app, or click the [Run in Insomnia](#insomnia) button.

## Middlewares

### checksExistsUserAccount

This middleware is responsible for receiving `username` via header and validating if this user exists. In case it exists, the user will be sent to the request and the `next` function will be called.

### checksCreateTodosUserAvailability

This middleware should receive `user` from the request and call the `next` function only if this user is on the Free plan and has created less than 10 <i>todos</i> OR if the user has the Pro plan activated.

### checksTodoExists

This middleware should receive `username` from the header and a task `id` from `request.params`. The middleware should validate the user, check if the `id` is of type `uuid` and check if `id` belongs to a <i>todo</i> from the informed user. After all the validations, the <i>todo</i> and the user should be sent to `request`, and the `next` function must be called.

### findUserById

This middleware is similar to <a href="#checksExistsUserAccount">checksExistsUserAccount</a>, but the search for the user must be done using the `id` passed through the route parameters. If the user is found, it should be sent to `request.user` and the `next` function must be called.

## Running the tests
To run the tests using Jest:
```
$ yarn test
```

![Jest output](/assets/test_evidence.png)

#

<p align="center">Developed by <a href="https://www.linkedin.com/in/marialuizasalviano/">Maria Luiza Salviano</a></p>