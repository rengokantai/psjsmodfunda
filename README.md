#### psjsmodfunda
#####3 expose module pattern.
singleton
```
var lowercase = function(){
    function c(){}
    return{
      c:c
    }
}();
```
constructor
```
var Uppercase = function(){};
var u = new Uppercase();
u.method();
```
#####4 module formats and loaders
singleton
```
var lowercase = function(){
    function c(){}
    return{
      c:c
    }
}();
```

```
define(['./a','./b'],function(a,b){
    function c(){}
    return{
      c:c
    }
});
```
######webpack in amd
```
./node_modules/.bin/webpack js/app.js build/bundle.js
```
######webpack in es2015
```
npm install babel-cli babel-es2015-preset babel-loader babel-core --save-dev http-server webpack
```
sample webpack.config.js
```
module.exports = {
  entry:'./js/app.js',
  output:{
    path: './build',
    filename: 'bundle.js',
  },
  module:{
    loaders:[{
      test:/\.js$/,
      exclude: /node_modules/,
      loader: 'babel-loader',
      query:{
        presets:['es2015']
      }
    }]
  }
}

