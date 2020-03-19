# Learning about Webpack

Webpack is a static module bundler. It creates a dependency graph by the relationships between files that are created with 'import' and 'require' statements. It uses this to create one JS file containing the code from all the modules in the correct order. The final bundled JS file is then served in the HTML file.

## The main concepts of Webpack

**Entry**. The entrypoint is the module/file that Webpack uses to start building the dependency graph. It uses this figure out which modules and libraries this entrypoint depends on and builds the graph until there's no dependency left. The default entrypoint is `./src/index.js` but we can specify a different entrypoint(s) in the Webpack config file.

**Output**. The output is the property that tells Webpack where to emit the bundled file and what to name it. The defult is `./dist/main.js` for the main bundle and `./dist` for other for other files generated (like images).

**Loaders**. Webpack uses loaders to process and convert files that are not JS or JSON into valid modules.

**Plugins**. Plugins provide solutions for asset management, optimisation, etc. Here I've used a HTMLWebpackPlugin to update the script output file automatically when the filename is changed.

**Mode**. Devs typically work in development mode or production mode. We can set which type of build we want by changing the mode parameter which tells Webpack which built-in optimisations to use.

### Webpack configuration

The `webpack.config.js` file describes how the files and assets should be transformed and what the output should be. It starts with the entrypoint and output. For any non-JS files, you add the loaders in the module rules. This is also where the dev server should be configured. Lastly comes the plugins.
