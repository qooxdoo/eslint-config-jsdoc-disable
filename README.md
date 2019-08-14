# eslint-jsdoc-qx

a disable configuration for jsdoc

## Install

```
$ npm install --save @qooxdoo/eslint-jsdoc-qx
```

For the `esnext` version you'll also need Babel's ESLint [parser](https://github.com/babel/babel-eslint) and [plugin](https://github.com/babel/eslint-plugin-babel):

```
$ npm install --save-dev babel-eslint eslint-plugin-babel
```

This will let you use ES2016 features like [`async`/`await`](https://github.com/lukehoban/ecmascript-asyncawait) and [decorators](https://github.com/wycats/javascript-decorators). For a full list of features see [Babel's experimental features](https://babeljs.io/docs/usage/experimental/) and their [Learn ES2015](https://babeljs.io/docs/learn-es2015/).


## Install in a existing Qooxdoo Project


### If you don't have a `package.json`

Create a new file `package.json` with the following contents in your project:

```json
{
  "name": "<appname>",
  "description": "<appdesc>",
  "author": "Your Name <your@email.com>",
  "version": "0.0.1",
  "license": "MIT",
  "dependencies": {},
  "devDependencies": {
    "@qooxdoo/eslint-config-qx": "^0.0.7"
  },
  "engine": "node >= 4.5",
  "eslintConfig": {
    "extends": [
      "qx"
    ]
  },
  "scripts": {
    "eslint": "eslint --cache"
  }
}
```

Replace name, description and author ofc.


### If you have a `package.json`

Add these lines to it:

```json
{
	"devDependencies": {
		"@qooxdoo/eslint-config-qx": "^0.0.7"
	},
	"eslintConfig": {
		"extends": [
			"@qooxdoo/eslint-config-qx/browser"
		]
	},
	"scripts": {
		"eslint": "eslint --cache"
	}
}
```


### Adjust your .gitingore

Add `.eslintcache` to it.


### Now install `eslint` and `eslint-config-qx`

```bash
$ npm install
```

### And finaly lint your files

```bash
$ npm run eslint -- .
```

Or lint AND fix:
```
$ npm run eslint -- --fix .
```

### Handling globals

Normaly your app has its own globals, like `qxl` for Qooxdoo Contribs,
for that you need to extend `@qooxdoo/eslint-config-qx/browser` with your own config.

Create a file `.eslintrc-qx`:

```json
{
  "globals": {
    "qxl": false
  }
}
```

This file tells eslint to ignore `qxl` but don't allow writes to it.

Now you need to tell eslint about it in `package.json`:

```json
{
	"eslintConfig": {
		"extends": [
			"@qooxdoo/eslint-config-qx/browser"
			".eslintrc-qx"
		]
	}
}
```

Thats all.


### Ignore compiled stuff in `.eslintignore`

ESLint has its own `.eslintignore` file, when you run `npm run eslint .` it will lint
all JS files found including generated ones, to exclude them you can create a
`.eslintignore` and files/directories to it like in `.gitignore`.

This is mine:

```
build/
gh-pages/
node_modules/
source/script/
source/resource/

# No need for lint
Gruntfile.js
```


## Usage

```json
{
	"extends": "@qooxdoo/eslint-jsdoc-config"
}
```


## Authors

- Henner Kollmann: [hkollmann](Henner.Kollmann@gmx.de)


## License

MIT
