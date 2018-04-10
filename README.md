# React Native Code Snippets for WebStorm IDE

## Summary

* [Installation](#installation)
* [Usage](#usage)
  * [Component](#component)
  * [Redux](#redux)
  * [Reactotron](#reactotron)

### Installation

To install Snippets on IDE, import file `settings.jar` from menu **File > Import Settings**.

## Usage
### Component

#### [rnc] - Create React Native Stateful Component

```javascript
import React, { Component } from 'react';

import { View } from 'react-native';

// import styles from './styles';

export default class MyComponent extends Component {
  render() {
    return (
      <View />
    );
  }
}
```

#### [rnstc] - Create React Native Stateless Component

```javascript
import React from 'react';

import { View } from 'react-native';

// import styles from './styles';

const MyComponent = () => (
  <View />
);

export default MyComponent;
```

#### [styles] - Create Styles File

```javascript
import { StyleSheet } from 'react-native';
// import { colors, fonts, metrics } from 'styles';

const styles = StyleSheet.create({});

export default styles;
```

#### [ctor] - Create Stateful Component Constructor Method

```javascript
constructor(props) {
  super(props);
  this.state = {};
}
```

#### [render] - Create Stateful Component render method

```javascript
render() {
  return (
    <View />
  );
}
```

### Redux

#### [reduxsetup] - Create Redux Setup file

```javascript
import { combineReducers } from 'redux';

/* Reducers */
// import navReducer from 'navigation/reducer';

import configureStore from './configureStore';
// import rootSaga from './sagas';

export default () => {
  const rootReducer = combineReducers({
    // nav: navReducer,
  });

  return configureStore(rootReducer, rootSaga);
};
```

#### [configurestore] - Create Configure Store file

```javascript
import { createStore, applyMiddleware, compose } from 'redux';

export default rootReducer => {
  const middleware = [];
  const enhancers = [];

  /* Saga */
  // const sagaMonitor = __DEV__ ? console.tron.createSagaMonitor() : null;
  // const sagaMiddleware = createSagaMiddleware({ sagaMonitor });
  // middleware.push(sagaMiddleware);

  enhancers.push(applyMiddleware(...middleware));

  /* Store */
  const createAppropriateStore = __DEV__
    ? console.tron.createStore
    : createStore;
  const store = createAppropriateStore(rootReducer, compose(...enhancers));

  /* Run Saga */
  // sagaMiddleware.run(rootSaga);

  return store;
};
```

#### [rncredux] - Create React Native Stateful Redux Component

```javascript
import React, { Component } from 'react';

import { View } from 'react-native';

import { connect } from 'react-redux';

// import styles from './styles';

class MyComponent extends Component {
  render() {
    return (
      <View />
    );
  }
}

const mapStateToProps = state => ({});

const mapDispatchToProps = dispatch => ({});

export default connect(mapStateToProps, mapDispatchToProps)(MyComponent);
```

#### [rnstcredux] - Create React Native Stateless Redux Component

```javascript
import React from 'react';

import { View } from 'react-native';

import { connect } from 'react-redux';

// import styles from './styles';

const MyComponent = () => (
  <View />
);

const mapStateToProps = state => ({});

const mapDispatchToProps = dispatch => ({});

export default connect(mapStateToProps, mapDispatchToProps)(MyComponent);
```

### Reactotron

#### [reactotronconfig] - Create Reactotron Config

```javascript
import Reactotron from 'reactotron-react-native';

if (__DEV__) {
  const tron = Reactotron
    .configure()
    .useReactNative()
    .connect();

  tron.clear();

  console.tron = tron;
}
```