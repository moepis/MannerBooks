---
title: "🍵 命名規則"
---
## はじめに
名は体を表します。
読むだけで意味がわかる具体的な命名を心掛けましょう！

:::details 命名の例(※筆者が好きなツイートです)
@[tweet](https://twitter.com/hal_cha_n/status/1046371478910844930?s=20)
:::

とはいえ、命名は一朝一夕にはいきません。
そのため、
①具体的な命名を少しずつ意識していくこと
②先人の知恵を借りること
この2つをお勧めします。
(偉そうに言っている私も、命名する際は毎回頭を抱えています)

## 命名規則とは？
そもそも命名規則とはなんでしょうか？ずばり、名前の付け方ルールです。
例えば複数の単語をつなぐ時は `user_id` のように `_`(アンダースコア) でつなぎなさい、はたまた `userId` のように2つ目以降の単語の頭文字を大文字にしなさいのような、変数や関数に名前を付ける際に守らないといけないルールのことです。

それでは命名のポイントをいくつか紹介します。

## 命名のポイント
### 1.明確で具体的な単語にしよう

- × 曖昧な単語
	-  `filter`
		-  選択しているのか、除去しているのか曖昧になってしまう
- ◎ 具体的な単語
	-  `select`, `exclude`
		-  選択しているのか、除去しているのか明確
- × 汎用的な名前を避ける
	- `size`, `tmp` など

### 2.長い名前を避けよう
- 単語の意味を保ったままコードが読みやすい長さ
	- `evaluation` -> ◎ `evel`
	- `document` -> ◎ `doc`
	- ※ただし、固有名詞やプロジェクト独自の単語の場合は、省略せず長いまま使用した方が良い
- 長くでも20文字以内にする

### 3.接頭辞、接尾辞を使用して情報を追加しよう
- 接頭辞、接尾辞に情報量を入れる
	- isEnabled
	- getAccount
- 単位などを入れることもある
	- `px`
	- `ms`

### 4.名前のフォーマットを整えよう
- 以下で説明します

## 命名フォーマットとは
変数や関数を定義する際のフォーマットを紹介します。
どの様なフォーマットが存在するのか見てみましょう！

:::details キャメルケース🐫
- 単語同士を大文字で繋ぐ
	- ラグダ(キャメル)のコブの様に見えるためキャメルケースと呼ばれる
		- `camelCase`
:::

:::details スネークケース🐍
- 単語同士をアンダーバー/アンスコで繋ぐ
	- スネーク(へび)の様に見えるためスネークケースと呼ばれる
		- `snake_case`
:::

:::details パスカルケース🦎
- 最初から大文字、単語の先頭を大文字で繋ぐ
- プログラミング言語Pascalで使われていたことからパスカルケースと呼ばれる
	- `PascalCase`
:::

:::details ケバブケース🍗/チェインケース⛓
- 単語同士をハイフンで繋ぐ
- 単語を肉、ハイフンを串に見立てた串焼きケバブの様に見えるためケバブケースと呼ばれる
- 単語をチェーン (鎖) で繋いでいる様に見えるためチェインケースと呼ばれる
	- `Kebap-case`
	- `chain-case`
:::

:::details コンスタントケース
- 全て大文字で単語同士をアンダーバー/アンスコで繋ぐ
- constant(定数)によく使われる記述のためコンスタントケースと呼ばれる
	- `CONSTANT_CASE`
:::

つまり、これだけ命名のフォーマットが存在します。

```javascript:命名フォーマット一覧
const camelCase = "キャメルケース";
const snake_case = "スネークケース";
const PascalCase = "パスカルケース";
const CONSTANT_CASE = "コンスタントケース";
```

JavaScriptではハイフン(-)の変数・関数名を許可していません。
理由は、ハイフン(-)が演算子のマイナスとして認識されてしまうためです。

ケバブケースやチェインケースはHTMLの要素などで利用されています。
```html:htmlのClass名
<dic class="Kebap-case">ケバブケース</div>
<dic class="chain-case">チェインケース</div>
```

プログラミング言語や、プロジェクトのルールによりますが、**定数をコンスタントケース**、**変数や関数はキャメルケース または スネークケース**とするパターンが多いです。コーディングをする前に統一したルールを設けておくと、複数人で開発した際もコードがバラバラにならないですね！
- [変数名の命名規則/＊＊ケースの使い分け
](https://qiita.com/am_nimitz3/items/7b01af53751dba5d8fb1)


### 命名どうする？クイズ

6問命名クイズを作成しました。
一緒に命名を考えてみて下さい。

:::details レコードを取得する関数名
```javascript
// Good(1レコードの場合)
function getRecord() {
}

// Good(複数レコードの場合)
function getRecords() {
}
```
:::

:::details アカウントを承認する関数名
```javascript
// Good
function acceptAccount() {
}
```
:::

:::details アカウントの権限を取り下げる関数名
```javascript
// Good
function revokeAccount() {
}
```
:::

:::details 事前テストをする関数名
```javascript
// △直訳
function testBerofe() {
}

// Good
function preTest() {
}
```
:::

:::details 再登録をする関数名
```javascript
// Good
function resend() {
}

// Good
function reregister() {
}
```
:::

:::details 更新可能か確認する関数
```javascript
// Good
function is_updatable() {
}
```
:::

いかがでしたか。
上記の命名が絶対ではありませんので、今後の命名の際のヒントにしてみて下さい。

## まとめ
変数名・関数名を定義した際に、「この名前で大丈夫かな？」と不安になった時は、命名した単語を読んでreturn値をイメージしたときに、命名した単語と値に誤差がないか確認してみましょう。もし何か違和感があれば、まだ抽象度が高い可能性があります。命名ポイントや先人の知恵を借りて、修正してみてください。

## チェックポイント
- [x] 命名のポイントが分かった
- [x] 命名フォーマットが分かった

### 参考記事
[コーディングの命名規則一覧](https://murashun.jp/article/programming/naming-conventions.html)
[メソッド名をシンプルにするために、
知っておくと便利な英語のprefixとsuffix](http://blog.codic.jp/2014/12/22/shoud-know-prefix-suffix-for-naming/)
[リーダブルコード](https://www.oreilly.co.jp/books/9784873115658/)