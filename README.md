# gs-redux
Redux-like library for Google Apps Scripts

## Usage

### 1. Add to your project `src` folder as Git submodule

```BASH
cd dist
git submodule add https://github.com/Glajik/gs-redux.git
```

### 2. Setup your .claspignore file

If you don't have it, create it in the same folder where is `.clasp.json` file.

Example of `.claspignore` file

```TEXT
# Ignore all submodule's folders, except '*.js'
gs-redux/**
!gs-redux/*.js
```

### 3. Use it

```JS
// Describe reducer, that describe state calculation
const reducer = (state = 0, action) => {
    switch (action.type) {
      case 'INCREMENT':
        return state + 1;
      case 'DECREMENT':
        return state - 1;
      default:
        return state;
    }
  };

// Create store
const store = createStore(reducer);

// Dispatch action
store.dispatch({ type: 'INCREMENT' });

// Get state
store.getState(); // 1

// See more usage examples in file __tests__/redux.test.js
```

### Update dependency

From your root of project run

```BASH
git submodule update --remote
```
