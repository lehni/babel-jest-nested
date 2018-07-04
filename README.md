# babel-jest-nested

[Babel](https://github.com/babel/babel) [jest](https://github.com/facebook/jest)
plugin

## Usage

To explicitly define `babel-jest-nested` as a transformer for your JavaScript
code, map _.js_ files to the `babel-jest-nested` module.

```js
transform: {
  '^.+\\.jsx?$': 'babel-jest-nested'
}
```

> Note: If you are using babel version 7 you have to install `babel-jest` with
>
> ```bash
> yarn add --dev babel-jest babel-core@^7.0.0-0 @babel/core
> ```

## Example with Lerna:

1. Specify the Lerna packages as Jest projects at the root level of your
    mono-repo in `jest.config.js`:

    ```js
    module.exports = {
      projects: ['<rootDir>/packages/*']
    }
    ```

2. Create a `jest.base.config.js` on the root level that each project / package
    will load, in which you use `babel-jest-nested` as the transformer:

    ```js
    module.exports = {
      transform: {
        '^.+\\.jsx?$': 'babel-jest-nested'
      }
    }
    ```

3. Then, within each Lerna package, simply provide a `jest.config.js` file that
    redirects to `jest.base.config.js`:

    ```js
    module.exports = {
      ...require('../../jest.base.config.js')
    }
    ```

4. Bingo!