# JavaScript formatting rules

Formatting rules for various JavaScript development configurations.

I generally adopt a relaxed (as opposed to compact) two-space identation style,
and I avoid error-prone constructs. This is similar to the style guides at
[Airbnb](https://github.com/airbnb/javascript) and Stripe, two of my former
employers.

## What's available

The repository contains **linter rules** arranged in subdirectories by
**JavaScript version** and **build target**.

**Linters**:

* [JSCS](http://jscs.info), for nagging people who don't use semicolons.
  (_Really?_)
* [JSHint](http://jshint.com/), for catching potential semantic issues.

**Versions:**

* [ES5](https://gist.github.com/sym3tri/2425983)
* [ES6](https://github.com/lukehoban/es6features), also known as _ES2015_.

**Targets:**

* [Browserify](http://browserify.org), for browser-based libraries.
  (I haven't jumped on the [Webpack](https://webpack.github.io) bandwagon yet.)
* [node.js](http://nodejs.org), for servers and scripts.

## How to use in a project

First, install this package via `npm`:

```bash
npm install --save-dev jamesreggio/javascript
```

Then, create a symbolic link between the files under `node_modules` and the
root of your repository. For example:

```bash
ln -s node_modules/javascript/es6/browserify/.jscsrc .jscsrc
ln -s node_modules/javascript/es6/browserify/.jshintignore .jshintignore
ln -s node_modules/javascript/es6/browserify/.jshintrc .jshintrc
```

Once the links are in place, run the linters from the root of your repository.
For example:

```bash
jscs src
jshint src
```

For node.js projects, the [`scripts.test` entry](https://github.com/jamesreggio/http-playground/blob/master/package.json)
in the package.json is a good place to run linters. For Browserify, include
them in the [build process](https://github.com/jamesreggio/unravel/blob/master/Makefile).

## Why I'm publishing this

I'm a tidy person and I like my code to be consistent. It is difficult for me
to ignore syntax in a code review, so I ask that you run these rules against
your code before contributing to one of my open-source repositories. The build
system should run these by default.

If you're reading this, you're probably annoyed with me, but that's okay. I
love you anyway <3
