# Japan Postal code oasis

JavaScript module for Japan Postal Code.

Forked from https://github.com/mzp/japan-postal-code

## Features

* ES6 modules
* Promise
* No denpendency (remove jsonp, you can choose bundle version or host it your self)
* Customize data url

## How to install
```
npm install japan-postal-code-oasis
```

## How to use

```js
const postal = import 'japan-postal-code-oasis';

postal('1000001', 'DATA_URI_BASE').then(addressa => {
  console.log(address.prefecture); // => "東京都"
  console.log(address.city); // => "千代田区"
  console.log(address.area); // => "千代田"
  console.log(address.street); // => ""
});
```

## LICENSE
MIT License
