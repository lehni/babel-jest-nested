# babel-jest-nested

[Babel](https://github.com/babel/babel) [jest](https://github.com/facebook/jest) plugin

## Usage

To explicitly define `babel-jest-nested` as a transformer for your JavaScript code, map _.js_ files to the `babel-jest-nested` module.

```json
"transform": {
  "^.+\\.jsx?$": "babel-jest-nested"
},
```

> Note: If you are using babel version 7 you have to install `babel-jest` with
>
> ```bash
> yarn add --dev babel-jest babel-core@^7.0.0-0 @babel/core
> ```
