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