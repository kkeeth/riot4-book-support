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

1つ目の `app.riot` の記述について．

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

`main.js` について．

```diff
  import '@riotjs/hot-reload'
  import {component} from 'riot'
+ // import 'ress'
  + import 'semantic-ui-riot'
  import App from './app.riot'
```
