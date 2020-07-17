#  Bug Report

Parcel with source maps enabled cannot import ckeditor5 Editor

##  Configuration (.babelrc, package.json, cli command)
```json
{
  "name": "parcel-ckeditor",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "parcel build index.js"
  },
  "author": "",
  "license": "ISC",
  "dependencies": {
    "@ckeditor/ckeditor5-build-classic": "^20.0.0",
    "@ckeditor/ckeditor5-react": "^2.1.0",
    "parcel-bundler": "^1.12.4",
    "react": "^16.13.1",
    "react-dom": "^16.13.1"
  }
}
```

##  Expected Behavior

`import ClassicEditor from '@ckeditor/ckeditor5-build-classic'` should work

##  Current Behavior

```
> parcel build index.js

⚠️  Could not load existing sourcemap of "node_modules/@ckeditor/ckeditor5-build-classic/build/ckeditor.js".
🚨  parcel-ckeditor/node_modules/@ckeditor/ckeditor5-build-classic/build/ckeditor.js:5:6589: Unexpected token (5:6589)
  3 |  * For licensing, see LICENSE.md.
  4 |  */
> 5 | !function(t){const e=t.en=t.en||{};e.dictionary=Object.assign(e.dictionary||{},{"%0 o ...
```

## Reproduce

```shell
npm install
npm run start
```