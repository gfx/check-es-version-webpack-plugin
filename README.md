# check-es-version-webpack-plugin

If your project supports IE11, you have to ensure your JavaScript bundles does not include ES2015+ syntax such as classes, async/await,

## SYNOPSIS

```js
// in webpack.config.js

const { CheckEsVersionPlugin } = require("check-es-version-webpack-plugin");

const config = {
  // ...
};

if (productionMode) {
  // this plugin works only for production mode,
  // because webpack wraps the input with eval() in development mode.
  config.plugins.push(new CheckEsVersionPlugin({
    esVersion: 5, // optional; 5 by default
  });
}

// ...
```

## How to check the ES version

This module uses [acorn](https://github.com/acornjs/acorn) to parse sources with a specified ES version.

That is, `acorn.parse(source, { ecmaVersion: 5 })` throws `SyntaxError` if the `source` includes ES2015 syntax like classes.

## LICENSE

ISC License

Copyright (c) 2018, Bit Journey, Inc.

Permission to use, copy, modify, and/or distribute this software for any purpose with or without fee is hereby granted, provided that the above copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
