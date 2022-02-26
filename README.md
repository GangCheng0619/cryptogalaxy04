![Blockchain-gaming](https://user-images.githubusercontent.com/92837296/151368512-b4343cb2-ea9f-4997-8fa1-d7f189f7b401.jpg)

This Golden Pig is an experienced developer and system analyst who now specializes in blockchain ecosystem development. 
He is comfortable working with many languages and platforms and has recently dedicated himself to developing blockchain applications using Solidity, Rust and MongoDB. He also has wide range of and deep experience with blockchain game development, and a master's degree in applied software engineering. 
He guaranteed a high quality of work and keep good communication. Working with a team of programmers during some of his projects, he provided readable, well commented and structured code. 
His goal is to provide high-quality service and products to his clients. He always ensure follow-up support after project completion.

* 🥇 Frontend Development: [Javascript](https://www.javascript.com/), [Typescript](https://www.typescriptlang.org/), [React.js](https://reactjs.org/), [Next.js](https://nextjs.org/) ), [Vue.js](https://vuejs.org/) ( [Nuxt.js](https://nuxtjs.org/), [Vuetify](https://vuetifyjs.com/)), [Angular](https://angular.io/) ( js, 2.0, 4.0, 5.0, 6.0, 7.0, 8.0, 9.0, 10.0 )
* 🥇 Backend Development: [Node.js](https://nodejs.org) ( [Hardhat.js](https://hardhat.org/), [Nest.js](https://nestjs.com/),  [Remix](https://remix.ethereum.org/) [Truffle](https://trufflesuite.com/), [Python](https://www.python.org/) ( [Django](https://www.djangoproject.com/) ), [Java](https://www.java.com/) ( [Spring](https://spring.io/) )
* 🥇 Hybrid Mobile App Development: [React-Native](https://reactjs.org/), [Ionic](https://ionicframework.com/), [NativeScript](https://nativescript.org/), [Flutter](https://flutter.dev/), [Xamarin](https://dotnet.microsoft.com/apps/xamarin)
* 🥈 DevOps: [CircleCI](https://circleci.com/), [Jenkins](https://www.jenkins.io/), [Github Actions](https://docs.github.com/en/actions), [Bitbucket Pipeline](https://bitbucket.org/product/features/pipelines), [Bitrise](https://www.bitrise.io/)
* 🥉 Test Framework: [Jest](https://jestjs.io/), [Mocha](https://mochajs.org/)/[Chai](https://www.chaijs.com/), [Protractor](https://www.protractortest.org), [Jasmine](https://jasmine.github.io/)

Here is my [eMail](mailto:passiondev5555@gmail.com?Subject=Hello%20cryptogalaxy04!) and [Skype](https://join.skype.com/invite/ulHRrEug5SCB).
Here is my [eMail](mailto:passiondev5555@gmail.com?Subject=Hello%20cryptogalaxy04!) and [Skype](https://join.skype.com/invite/dlJFnBUSkPkN).

# redux-execute [![Maintainability](https://api.codeclimate.com/v1/badges/1448aef0f57513e42c0c/maintainability)](https://codeclimate.com/github/sergeysova/redux-execute/maintainability) [![Build Status](https://travis-ci.com/sergeysova/redux-execute.svg?branch=master)](https://travis-ci.com/sergeysova/redux-execute) [![Coverage Status](https://coveralls.io/repos/github/sergeysova/redux-execute/badge.svg?branch=master)](https://coveralls.io/github/sergeysova/redux-execute?branch=master)

## Readme

## Installation

> Note: redux-execute requires redux@^4.0.0

```sh
npm install --save redux-execute
```

ES modules:

```js
import { createExecue } from "redux-execute"
```

CommonJS:

```js
const { createExecue } = require("redux-execute")
```

## Why do I need this?

Please, read [introduction to thunks in Redux](https://stackoverflow.com/questions/35411423/how-to-dispatch-a-redux-action-with-a-timeout/35415559#35415559). Execue just another way to run and test thunks(effects).

## Motivation

Redux Execue [middleware](https://github.com/reactjs/redux/blob/master/docs/advanced/Middleware.md) allows you to write "action creators" that return function instead of an action. These action creators are called effects. The effect can be used to delay the dispatch an action, or to dispatch another effect, or to dispatch only if a certain condition is met. The inner function receives the store methods `dispatch` and `getState` as parameters.

An action creator that returns a function to perform asynchronous dispatch:

js
const setValue = (value) => ({
  type: "SET_VALUE",
  payload: { value },
})

const setValueWithDelay = (value) => (dispatch) => {
  setTimeout(() => {
    // classic dispatch action
    dispatch(setValue(value))
  }, 1000)
}
```

Effect that dispatch another effects:

```js
const incrementWithDelay = () => (dispatch, getState) => {
  const { value } = getState()

  // Just pass effect and all arguments as arguments of dispatch
  dispatch(setValueWithDelay, value + 1)
}
```

## What is an effect?

An effect is a [thunk](https://en.wikipedia.org/wiki/Thunk) that called by `dispatch`.

```js
const effect = (a, b) => (dispatch, getState) => {
  return a + b
}

store.dispatch(effect, 1, 2) // 3
```

[See also](https://github.com/cryptogalaxy04/redux-thunk#whats-a-thunk)

## Composition

Any return value from the inner function of effect will be available as the return value of `dispatch` itself. This is convenient for orchestrating an asynchronous control flow with effects dispatching each other and returning Promises to wait for each other's completion.

```js
const requestGet = (url) => () =>
  fetch(`/api${url}`).then((response) => response.json())

const userPostsFetch = (userId) => async (dispatch) => {
  const user = await dispatch(requestGet, `/users/${userId}`)

  if (user.isActive) {
    return dispatch(requestGet, `/users/${userId}/posts`)
  }

  return []
}
```

## Logger

Redux Execue has logger out of the box. You can combine it with [redux-logger](https://github.com/cryptogalaxy04/redux-logger):

```js
import { createStore, applyMiddleware } from "redux"
import { createLogger } from "redux-logger"
import { createExecue } from "redux-execute"

import { rootReducer } from "./reducers"

const store = createStore(
  rootReducer,
  applyMiddleware(
    createExecue({ log: true }),
    createLogger({ collapsed: true }),
  ),
)
```
