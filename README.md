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
- そういう時に使うのが`computed プロパティ`
```javascript
        computed: {
          lessThanThree: function () {
            return this.counter > 3 ? "3より大きい" : "３以下";
          },
        },
```
- methodとは違う
	- computedの方は依存関係によってキャッシュされる
	- methodはテンプレートに変化が起きて、再描画されるごとに実行される
	- computedの方は、参照先が変化したときのみに実行される

# 27 ウォッチャを使って、データが変わったときに処理を実行する
- 似たようなものなので、基本的にcomputed プロパティを使う
- 使えないときにしゃーなし使う
- computedはプロパティーなので、画面に表示しないと実行されない
- 表示はしないけど、裏で監視したり、処理を実行したいときに使う
- 非同期処理はreturn できない

# 28
- computed プロパティについては、絶対に()をつけない
- methodsは基本的につけて統一した方が良さそう
	- v-onディレクティブはつけてもつけなくてもよい
	- {{}}内の場合はjs式を記述する必要があるので、必ずつける

## 37
`v-else` は`v-if`の直下でなければならない

## 40
- `v-show`も`v-if`と同じように使うことができる
- `v-show`は`display: none`として、画面に表示していないだけ。
  - デメリットあるので、基本的に使わない？
  - 頻繁に表示の切り替えをする場合は`v-show`を使った方が良い