# JavaScript formatting rules

Formatting rules for various JavaScript development configurations.

I generally adopt a relaxed (as opposed to compact) two-space identation style,
and I avoid error-prone constructs. This is similar to the style guides at
[Airbnb](https://github.com/airbnb/javascript) and Stripe, two of my former
employers.

## What's available?

The repository contains **linter rules** arranged in subdirectories by
**language** and **target**.

**Linters**:

* [JSCS](http://jscs.info), for nagging people who don't use semicolons.
  (_Really?_)
* [JSHint](http://jshint.com/), for catching potential semantic issues.

**Languages:**

* ES5
* ES6

**Targets:**

* [Browserify](http://browserify.org), for projects that use browser globals.
* [node.js](http://nodejs.org), for obvious reasons.

## How do I use this?

First, install this package via `npm`:

```sh
npm install --save-dev jamesreggio/javascript
```

Then, create a symbolic link between the files under `node_modules` and the
root of your repository. For example:

```sh
ln -s node_modules/javascript/es6/browserify/.jscsrc .jscsrc
ln -s node_modules/javascript/es6/browserify/.jshintignore .jshintignore
ln -s node_modules/javascript/es6/browserify/.jshintrc .jshintrc
```

## Why are you publishing this?

I'm a tidy person and I like my code to be consistent. It is difficult for me
to ignore syntax in a code review, so I ask that you run these rules against
your code before contributing to one of my open-source repositories. The build
system should run these by default.

If you're reading this, you're probably annoyed with me, but that's okay. I
love you anyway <3
