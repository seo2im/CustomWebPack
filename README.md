# WebPack Custom Package

> OBJECT

1. Knownledge what is **Webpack**
2. Knownledge what is **loader**
3. Write custom **webpack.config.js**
</br></br>

## What is webpack
**At its core, webpack is a static module bundler for modern JavaScript applications.**[--official--](https://webpack.js.org/concepts/)**Moulde** is sources, **bundle** is result. Compress and rewrite all sources related to thier relations for making bundle.
</br></br>

## How to work it
`webpack-cli` is command tool. install & exec below.

```shell
npm install webpack webpack-cli
npx webpack
```

Work in code possible. Espacially, When controling webpack carefully, like`next.js` or 'CRA', exec webpack in code.
</br></br>

## Basic setting

Webpack work with `webpack.config.js`. Set entry and output. input is start point of moudules, output is bundle.

```javascript
const path = require('path');

module.exports = {
	entry : 'index.js',
	output : {
		filename : 'bundle.js',
		path : path.resolve(__dirname, 'dist')
	},
	mode : 'production', //default optimazation system applied
	optimization : { minimizer : []} //This is compress setting not working
}
```

**Entry** is first point of our program. all relation start this file. **Output** is bundle file. This file 'immediately invoked function expression' for runtime code.
</br></br>

## Loader

**Loader** converts some modules(file) to some custom structive forms. For example, any file can convert js code with correct loader.</br></br>

For making code to ES5 code, use babel. If you want to more information about babel, ref [here](https://github.com/seo2im/CustomBabel). In webpack, use babel with `babel-loader`.

```javascript
module.exports = {
	/* ... */
	module : {
		rules : [ // module rule setting
			{
				test : /\.js/, //all js file
				exclude : /node_modules/, //npm module excluing
				use: 'babel-loader'
			}
		]
	},
	mode : 'production'
}
```

## Plugins



