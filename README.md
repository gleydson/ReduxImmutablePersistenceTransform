[![Build Status](https://travis-ci.com/gleydson/ReduxImmutablePersistenceTransform.svg?branch=master)](https://travis-ci.com/gleydson/ReduxImmutablePersistenceTransform)
[![npm version](https://badge.fury.io/js/redux-immutable-persistence-transform.svg)](https://badge.fury.io/js/redux-immutable-persistence-transform)

# Redux Immutable Persistence Transform

Library that allows you to transform immutable data created with **seamless-immutable** for use with **redux-persist**

## Why?

As of version 5 of redux-persist, the use of immutable states is no longer supported. In this way it is necessary to use a transformer that will carry out the conversion of its state to immutable data as necessary

## Installation

`yarn add redux-immutable-persistence-transform`

or

`npm i redux-immutable-persistence-transform`

## How to use?

```javascript
import { createStore } from "redux";
import { persistStore, persistReducer } from "redux-persist";
import storage from "redux-persist/lib/storage";
import { SeamLessImmutablePersistenceTransform } from "redux-immutable-persistence-transform";

import reducers from "./ducks";

const persistConfig = {
  key: "root",
  storage,
  transforms: [SeamLessImmutablePersistenceTransform]
};

const persistedReducer = persistReducer(persistConfig, reducers);

const store = createStore(persistedReducer);
const persistor = persistStore(store);

export { store, persistor };
```

## To Do

- [ ] Configure continuous integration with Travis
- [ ] Create transform for [`immutable`](https://github.com/immutable-js/immutable-js) library
- [ ] Add unit tests
- [ ] Add sample project

## License

Distributed under the MIT license. See `LICENSE` for more information.

## Contact

Gleydson Rodrigues - [Github](https://github.com/gleydson) - **gleydsonsr@gmail.com**
