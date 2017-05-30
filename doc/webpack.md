## Webpack ##

**Install with Yarn**
 
 [See Yarn usage](yarn.md)


     yarn add webpack webpack-dev-server --save
     

This command create new lines in your package Json and the yarn.lock file
     
     "dependencies": {
         "webpack": "^2.5.1",
         "webpack-dev-server": "^2.4.5"
      }
      
If there are errors like: _error webpack-dev-server@2.4.5: The engine "node" is incompatible with this module. Expected version ">=4.7"._
     
      --ignore-engines

To be sure that _webpack_ command is present in your PATH

     export PATH=node_modules/.bin:$PATH
     
**Webpack configuration sample (webpack.config.js)**


     const path = require('path');
     const webpack = require('webpack');
     module.exports = {
         context: path.resolve(__dirname, 'src'),
         entry: {
             app: './app.js',
         },
         output: {
             path: path.resolve(__dirname, 'dist'),
             publicPath: '/dist/',
             filename: '[name].bundle.js',
         },
         plugins: [
             new webpack.NamedModulesPlugin()
         ]
     };
     
Js files goes in src/app.js

**HTML**

    <!DOCTYPE html>
    <html>
       <head>
          <title>Webpack sample</title>
       </head>
       <body>
          <div id="app"></div>
          <script type="text/javascript" src="dist/app.bundle.js"></script>
       </body>
    </html>
    
    
**Webpack Dev server**

    webpack-dev-server --inline
    
See your application at  http://localhost:8080/    
