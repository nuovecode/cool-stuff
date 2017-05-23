## Babel ##

**Install with Yarn**

 [See Yarn usage](doc/yarn.md)

      yarn add babel-core babel-loader babel-plugin-transform-runtime babel-preset-es2015 --save
      
**ES6 transpile**
      
Add in [webpack.config.js](doc/webpack.md) the rules for ES6 
      
      module: {
          rules: [{
              test: /\.js$/,
              include: path.resolve(__dirname, 'src'),
              use: [{
                  loader: 'babel-loader',
                  options: {
                      plugins: ['transform-runtime']
                  }
              }]
          }]
      }
      
**Create .babelrc**
          
      {
        "presets": [
          ["es2015"]
        ],
        "plugins": ["babel-plugin-transform-runtime"],
        "comments": false
      }
      
      
      