# koa-static-prefix

## base on koa-static add 'prefix path'


[![NPM version][npm-image]][npm-url]
[![Build status][travis-image]][travis-url]
[![Test coverage][coveralls-image]][coveralls-url]
[![Dependency Status][david-image]][david-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

 Koa static file serving middleware, wrapper for [`koa-send`](https://github.com/koajs/send).

 addr: https://github.com/zhoushirong/koa-staitc-prefix.git

## Installation

```bash
$ npm install koa-static-prefix
```

## API

```js
const Koa = require('koa');
const app = new Koa();
app.use(require('koa-static-prefix')(root, opts));
```

* `root` root directory string. nothing above this root directory can be served
* `opts` options object.

## Example

```js
const serve = require('koa-static-prefix');
const Koa = require('koa');
const app = new Koa();

// $ GET /package.json
app.use(serve('.'));

// $ GET /hello.txt
app.use(serve('test/fixtures'));

// or use absolute paths
app.use(serve(__dirname + '/test/fixtures'));

app.listen(3000);

console.log('listening on port 3000');

app.use(serve(__dirname + '/test/fixtures', { pathPrefix:'/test' }));

```

