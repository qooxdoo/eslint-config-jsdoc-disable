# eslint-config-jsdoc

a disable configuration for jsdoc

## Install

```
$ npm install --save @qooxdoo/eslint-config-jsdoc-disable
```


## Usage

For ESLint 9+ (flat config):
```js
import jsdocDisable from '@qooxdoo/eslint-config-jsdoc-disable';

export default [
  ...jsdocDisable
];
```

For legacy ESLint (deprecated):
```json
{
	"extends": "@qooxdoo/jsdoc-disable"
}
```


## Authors

- Henner Kollmann: [hkollmann](Henner.Kollmann@gmx.de)


## License

MIT
