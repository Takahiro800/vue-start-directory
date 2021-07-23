## v-on イベントリファレンス
[イベントリファレンス | MDN](https://developer.mozilla.org/ja/docs/Web/Events)

## v-onディレクティブの引数（例・clickとか）を動的に渡す
```html
	<button v-on:[event]="countUp">count up!</button>
```
```javascript
	new Vue({
		el: "#app",
		data: {
			event: "click",
		},
	});

```

## v-onの省略
`@`を使う
- `v-on:click`と`@click`は同義

## v-modelの導入
- viewからmodelにデータを渡すことができるようになる
```javascript
	<input type="text v-model="message">
```

- こいつのおかげで双方向データビンディングが可能

# 25 computed プロパティについて
- dataは初期値のようなもので、動的に定義することはできない（条件分岐とかできない）