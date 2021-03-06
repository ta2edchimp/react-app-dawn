# react-app-dawn

It is likley the case that using one of the boilerplates list below is more than adequite for the average developer working on an average React app.

* [http://reactboilerplate.com](http://reactboilerplate.com)
* [redux-easy-boilerplate](https://github.com/anorudes/redux-easy-boilerplate)

This isn't a slight of the boilerplates or average developers. Both get the job done just fine in most situtaions.

However, a time will come when knowing the details off all aspects of a development stack will be required. When this happens you'll need something that is more boilerplate and less application seed. That is React App Dawn.

## Installation:

1. Install Node & npm
2. run > `npm i webpack-dev-server@2.1.0-beta.9 webpack@2.1.0-beta.25 eslint stylelint browser-sync rimraf -g` from a terminal
3. Download this repo, `cd` into the repo directory from a terminal and run > `npm install`
4. run > `npm run start:dev` this will open the app up in a web browser at localhost:8080

## npm CLI scripts:

| `npm run [name:name]` |Description (read comments in package.json for more details)|
|------------------|-----------|
|`npm run start:dev`|Start webpack dev server, serve `src` directory at localhost:8080 using hot reloading|
|`npm run build`|Create a build version (bundle, lint, minify etc..) of `src`, place that in the `build` directory|
|`npm run start:prod`|Start browser-sync, serve `build` directory at localhost:3000|
|`npm run lint:js`|lint all js files in `src` directory|
|`npm run lint:css`|lint all css file sin `src` directory|

## Broad description of tools used (including implementation deails):

#### Node Version Manager

* [Node Version Manager](https://github.com/creationix/nvm) is used to manage which version of node is used for this app.
* the [`.nvmrc`](.nvmrc) defines the current version of node.

#### Webpack 2

* Webpack 2 is used to take es2015 modules and translate them into a chunked format that can run in web browsers.
* The configuration file for webpack is [webpack.config.babel.js](webpack.config.babel.js). 
* By using babel in the name of the file the file, [webpack.config.babel.js](webpack.config.babel.js), it will be babalized before running.

#### Babel

* Webpack uses Babel to transform [latest](http://babeljs.io/docs/plugins/preset-latest/), [stage0](http://babeljs.io/docs/plugins/preset-stage-0/), and [react](http://babeljs.io/docs/plugins/preset-react/) code to ES5 code.

#### Polyfill Browser DOM and JS features

* The [`index.html`](src/index.html) page uses polyfill.io to fill any [missing modern browser features](https://polyfill.io/v2/docs/features/) (e.g. DOM & JS)

#### Linting

* Use eslint & stylelint, linters, configured from files found in `linters` directory

## Conventions used:

* Keep webpack config to a small single file that deals with both dev and production.
* Own the js and CSS linter rules (starting point taken from [eslint-config-airbnb](https://www.npmjs.com/package/eslint-config-airbnb) and [stylelint-config-standard](https://github.com/stylelint/stylelint-config-standard))
* Don't place unecessary configurations in package.json that can be contained in there own configuration file (e.g. .babelrc, .nvmrc, .eslintrc, .stylelintrc).
* Linting happens during development in the developers editor and at build time


