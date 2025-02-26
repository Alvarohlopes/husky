# husky

> Git hooks made easy

[![](https://img.shields.io/npm/dm/husky.svg?style=flat)](https://www.npmjs.org/package/husky) [![Mac/Linux Build Status](https://img.shields.io/travis/typicode/husky.svg?label=Mac%20OSX%20%26%20Linux)](https://travis-ci.org/typicode/husky) [![Windows Build status](https://img.shields.io/appveyor/ci/typicode/husky/master.svg?label=Windows)](https://ci.appveyor.com/project/typicode/husky)

Husky can prevent bad `git commit`, `git push` and more 🐶 _woof!_

## Sponsors

[__Support Husky on Open Collective and have your company logo here (starts from $100/m)__](https://www.opencollective.com/husky)

Visit [thanks.typicode.com](https://thanks.typicode.com) 🌵 to view all the people supporting husky.

## Install

```sh
npm install husky --save-dev
```

```js
// package.json
{
  "husky": {
    "hooks": {
      "pre-commit": "npm test",
      "pre-push": "npm test",
      "...": "..."
    }
  }
}
```

```sh
git commit -m 'Keep calm and commit'
```

To go further, see the docs [here](https://github.com/typicode/husky/blob/master/DOCS.md).

__Note__: there's a known issue with Node `v12.0`, please use `v12.1` or higher. 

## Uninstall

```sh
npm uninstall husky
```

## Upgrading from 0.14

Simply move your existing hooks to `husky.hooks` field and use raw Git hooks names. Also, if you're using the `GIT_PARAMS` env variable, rename it to `HUSKY_GIT_PARAMS`.

```diff
{
  "scripts": {
-   "precommit": "npm test",
-   "commitmsg": "commitlint -E GIT_PARAMS"
  },
+ "husky": {
+   "hooks": {
+     "pre-commit": "npm test",
+     "commit-msg": "commitlint -E HUSKY_GIT_PARAMS"
+   }
+ }
}
```

Alternatively, you can run the following command which will do the same automatically for you ;)

```
./node_modules/.bin/husky-upgrade
```

Starting with `1.0.0`, you can also configure hooks using `.huskyrc`, `.huskyrc.json` or `.huskyrc.js` file.

```js
// .huskyrc
{
  "hooks": {
    "pre-commit": "npm test"
  }
}
```

To view the full list of changes, please see the [CHANGELOG](https://github.com/typicode/husky/blob/master/CHANGELOG.md).

## Features

* Keeps existing user hooks
* Supports GUI Git clients
* Supports all Git hooks (`pre-commit`, `pre-push`, ...)

## Used by

* [jQuery](https://github.com/jquery/jquery)
* [babel](https://github.com/babel/babel)
* [create-react-app](https://github.com/facebookincubator/create-react-app)
* [Next.js](https://github.com/zeit/next.js)
* [Hyper](https://github.com/zeit/hyper)
* [Kibana](https://github.com/elastic/kibana)
* [JSON Server](https://github.com/typicode/json-server)
* [Hotel](https://github.com/typicode/hotel)
* ... and many other awesome projects

## See also

* [pkg-ok](https://github.com/typicode/pkg-ok) - Prevents publishing a module with bad paths or incorrect line endings
* [please-upgrade-node](https://github.com/typicode/please-upgrade-node) - Show a message to upgrade Node instead of a stacktrace in your CLIs
* [pinst](https://github.com/typicode/pinst) - dev only postinstall hook

## License

MIT
