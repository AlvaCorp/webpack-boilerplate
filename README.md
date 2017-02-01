## Webpack 2 Boilerplate

This boilerplate is designed to get you up and running with Webpack 2. It is minimally configured but supports native ES6 and ES6 modules using Babel.

#### Development Quickstart

1. Clone this repository to your local machine.
2. Run `yarn install` to install dependencies from your `package.json`. Don't have Yarn? Install it with `brew install yarn`.
3. Place source files for your client side code inside of the `./src` directory. 
4. Open the `webpack.config.js` and add starting source files to your `entry` file. Note the current entry file is `app.js` and there is currently an `./src/app.js`; you can add other source files as well.
5. Create an `index.html` HTML file in your `./src` directory and add a link to `<script src="app.bundle.js"></script>
` in your HTML file.
6. Run `yarn start` to begin running Webpack in production mode. Browse to `localhost:8080` to see your website.

#### Releasing for Production

* You can build an _unminified_ version of your source code by running `yarn build`. This will place the output files in your `/dist` directory. You'll just need to include those files in your HTML file(s) as needed.
* You can also build a _minified_ version of your source code by running `yarn prod`. This also places your code in the `/dist` folder. This is the best option to use for performance.

#### Debugging in the Browser

Webpack 2 provides source maps in the debug window of your browser. In the **sources** tab where all of your code is loaded, you'll notice a `webpack://` domain. Inside of that domain, a `~` folder exists - this is your raw Javascript code. You can place breakpoints here and debug as usual. It is awesome!

#### Lazy Loading

Webpack can load/import individual Javascript files as needed. In `/src/js/app.js` you'll notice that there is a `System.import()` for `LazyLoadingComponent.js`. This allows the developer to only load code as needed providing a better user experience. _Note_: you should provide some sort of user interface experience such as a loading bar to let the user know that there is something being performed in the background. 

#### Tree Shaking

Webpack 2 removes ES6 modules (anything using the `import ...` syntax) that aren't actually imported into your project through a technique called _tree shaking_. Notice that in your `build` or `prod` output, `/src/js/components/NotUseComponent.js` is not included in the output.