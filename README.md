# Translate Baidu2

free baidu translate

## Change Log

- [changelog.md](https://github.com/YLQZ/translate-baidu/blob/master/CHANGELOG.md)

## Features

- Auto language detection
- Spelling correction
- Language correction
- Fast and reliable – it uses the same servers that [fanyi.baidu.com](https://fanyi.baidu.com) uses

## Install

```
npm install --save translate-baidu
```

## Usage

```js
const translate = require('translate-baidu')

translate('hello')
	.then((res) => {
		console.log(res)
	})
	.catch((err) => {
		console.error(err)
	})

// => { from: "en", to: "zh", dst: "你好", src: "hello" }
```

## VS Translate Baidu

Translate Baidu cannot to translate Stitching strings
this will be OK

```js
const translate = require('translate-baidu')
const str = `
/**
 * Returns an iterator allowing to go through all key/value pairs contained in this object.
 */
`
translate(str)
	.then((res) => {
		console.log(res)
	})
	.catch((err) => {
		console.error(err)
	})

// =>
// {
//     from: 'en',
//     to: 'zh',
//     dst: '/**\n*返回一个迭代器，允许遍历此对象中包含的所有键/值对。\n*/\n',
//     src:'/**\n* Returns an iterator allowing to go through all key/value pairs contained in this object.\n*\n'
// }
```

## API

### translate(text, options)

#### text

Type: `string`
The text to be translated

#### options

Type: `object`

##### from

Type: `string` Default: `auto`
The `text` language. Must be `auto` or one of the codes/names (not case sensitive) contained in [languages.js](https://github.com/YLQZ/translate-baidu/blob/master/src/languages.js)

##### to

Type: `string` Default: `en`
The language in which the text should be translated. Must be one of the codes/names (not case sensitive) contained in [languages.js](https://github.com/YLQZ/translate-baidu/blob/master/src/languages.js).

##### full

Type: `Boolean` Default: false
Return to the Full Baidu translation result object

### Returns an `object`:

- `text` _(string)_ – The translated text.

```js
translate('Hello world', { from: 'en', to: 'nl' })
	.then((res) => {
		console.log(res)
		//=> { from: "en", to: "zh", dst: "你好，世界", src:"Hello world"}
	})
	.catch((err) => {
		console.error(err)
	})
```

### Base on

[Translate Baidu](https://github.com/shikar/NODE_BAIDU_TRANSLATE)

## License

MIT © [YLQZ](1194979849@qq.com)
