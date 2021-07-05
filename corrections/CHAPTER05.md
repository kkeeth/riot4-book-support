# CHAPTER 05 Riot.js でのスタイリング

#### ▼ P201（誤字）

```
誤: 外部ライブライブラリ
正: 外部ライブラリ
```

#### ▼ P201（誤植）

```
誤: これは個人的な見解ですが、78ページでもお話したように、
正: これは個人的な見解ですが、82ページでもお話したように、
```

#### ▼ P203（誤植）

```diff
  + anime({
- +   targets: 'li',
+ +   targets: 'li:last-child',
  +   translateX: [200, 0],
  +   delay: anime.stagger(100)
  + })
```

#### ▼ P215（誤植）

1 つ目の `app.riot` の記述について、スタイルの微調整のコードが抜けていました。

```diff
  + <style>
  +   :host {
  +     padding: 2rem;
  +   }
+ +   li {
+ +     list-style: none;
+ +     margin: 10px auto;
+ +   }
  + </style>
```

`main.js` について、コメントアウトしている行の記述が漏れていました。

```diff
    import '@riotjs/hot-reload'
    import {component} from 'riot'
+   // import 'ress'
  + import 'semantic-ui-riot'
    import App from './app.riot'
```

#### ▼ P231, 232（誤植）

以下コードの記述の 1 行の挿入位置が間違っておりました。

```diff
  + handleInput(e) {
  +   if (e.target.value.length > 0)
  +     this.errors.address = ""
  +   else
  +     this.errors.address = errorMessages.address
  +
- +   this.isTermCheck = !this.isTermCheck
  +   this.update()
  + },
  + handleChangeCheckbox(e) {
  +   if (e.target.checked)
  +     this.errors.agree = ""
  +   else
  +     this.errors.agree = errorMessages.agree
  +
+ +   this.isTermCheck = !this.isTermCheck
  +   this.update()
  + }
```
