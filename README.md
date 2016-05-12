# console-loader

[![npm](https://img.shields.io/npm/v/console-loader.svg?maxAge=2592000)](https://www.npmjs.com/package/console-loader)
[![GitHub issues](https://img.shields.io/github/issues/eedrah/console-loader.svg)](https://github.com/eedrah/console-loader/issues)
[![GitHub license](https://img.shields.io/badge/license-ISC-blue.svg)](https://raw.githubusercontent.com/eedrah/console-loader/master/LICENSE)

Print the resolved request of webpack to the console. Short and simple.

## Installation
Install via NPM
```
npm install console-loader --save-dev
```
or use directly
```js
require('/path/to/dir/of/console-loader/index.js!/path/to/file.js')
```

## Use and examples
```js
var React = require('console!react')
```
will display the following in the console when webpack is run:
```
/path/to/dir/node_modules/console-loader/index.js!/path/to/dir/node_modules/react/react.js
```

### Alternatively,
```js
// es6
import foo from 'console!./foo.js'
```
or
```js
// In webpack.config
module: {
    loaders: [{
        test: /\.css$/,
        loaders: ["style", "console", "css?sourceMap"]
    }]
}
```
which will display
```
/dir/node_modules/console-loader/index.js!/dir/node_modules/css-loader/index.js?sourceMap!/dir/my-file.js
```
Note that the query is displayed for all the loaders, and that the style loader is missing due to the [loader order](https://webpack.github.io/docs/loaders.html#loader-order).

## Contributions
Contributions are welcome! Feel free to log an issue or send a pull request if you would like to see options for
- trimmed output
- pretty output
- the source that is passed through the loader
- something else

## Licence
Open Source - ISC - See LICENCE file
