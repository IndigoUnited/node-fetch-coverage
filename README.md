# fetch-coverage

[![NPM version][npm-image]][npm-url] [![Downloads][downloads-image]][npm-url] [![Build Status][travis-image]][travis-url] [![Coverage Status][codecov-image]][codecov-url] [![Dependency status][david-dm-image]][david-dm-url] [![Dev Dependency status][david-dm-dev-image]][david-dm-dev-url] [![Greenkeeper badge][greenkeeper-image]][greenkeeper-url]

[npm-url]:https://npmjs.org/package/fetch-coverage
[downloads-image]:http://img.shields.io/npm/dm/fetch-coverage.svg
[npm-image]:http://img.shields.io/npm/v/fetch-coverage.svg
[travis-url]:https://travis-ci.org/moxystudio/node-fetch-coverage
[travis-image]:http://img.shields.io/travis/moxystudio/node-fetch-coverage/master.svg
[codecov-url]:https://codecov.io/gh/moxystudio/node-fetch-coverage
[codecov-image]:https://img.shields.io/codecov/c/github/moxystudio/node-fetch-coverage/master.svg
[david-dm-url]:https://david-dm.org/moxystudio/node-fetch-coverage
[david-dm-image]:https://img.shields.io/david/moxystudio/node-fetch-coverage.svg
[david-dm-dev-url]:https://david-dm.org/moxystudio/node-fetch-coverage?type=dev
[david-dm-dev-image]:https://img.shields.io/david/dev/moxystudio/node-fetch-coverage.svg
[greenkeeper-image]:https://badges.greenkeeper.io/moxystudio/node-fetch-coverage.svg
[greenkeeper-url]:https://greenkeeper.io/

Fetch the code coverage from an open-source GIT repository, using a variety of well-known coverage services.

Currently supports GitHub, Bitbucket and GitLab repositories and checks against [Coveralls](https://coveralls.io/), [Code Climate](https://codeclimate.com/), [Scrutinizer](https://scrutinizer-ci.com/) and [Codecov](https://codecov.io/).

Feel free to make a PR adding support for another coverage service.


## Installation

```sh
$ npm install fetch-coverage
```


## Usage

`fetchCoverage(repositoryUrl, options) -> Promise`

```js
const fetchCoverage = require('fetch-coverage');

fetchCoverage('git@github.com:moxystudio/node-planify.git')
 // `coverage` is a number between 0 and 1 or `null` if there's no code coverage
.then((coverage) => console.log('Coverage', coverage));
```

The `repositoryUrl` is any valid cloneable URL.

Available options:

- `branch`: The target branch (only supported in some services)
- `services`: The services to fetch from, defaults to all services
- `got`: Custom options to be passed to [got](https://github.com/sindresorhus/got), defaults to `{ timeout: 15000 }`
- `badges`: The badges information gathered by [detect-readme-badges](https://github.com/IndigoUnited/node-detect-readme-badges) which might speed up the  fetching process


## Tests

```sh
$ npm test
$ npm test -- --watch # during development
```


## License

Released under the [MIT License](http://www.opensource.org/licenses/mit-license.php).
