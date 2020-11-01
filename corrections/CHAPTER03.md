# CHAPTER 03 はじめての Riot.js でのアプリケーション開発

- P92（誤植）

Plunker の preview の URL はソースコードを変更して保存したり別ブラウザで閲覧するなどすると、変更することがあるため、書籍に記述した URL ではデモアプリを確認することができなくなってしまいました。

以下の URL にアクセスしてみてください。

```
誤: https://run.plnkr.co/preview/ck8em6dla001a2a6lbxtc9nbd/
正: https://plnkr.co/plunk/Uoghj8aOznPhxdoQ6GHJ
```

- P95（誤植）

ソースコード上のインデントが揃っていない。

```diff
  +   margin: 5% auto;
- + padding: 20px;
+ +   padding: 20px;
- + box-shadow:
- +   0 2px 2px 0 rgba(0,0,0,.14),
- +   0 3px 1px -2px rgba(0,0,0,.2),
- +   0 1px 5px 0 rgba(0,0,0,.12);
+ +   box-shadow:
+ +     0 2px 2px 0 rgba(0,0,0,.14),
+ +     0 3px 1px -2px rgba(0,0,0,.2),
+ +     0 1px 5px 0 rgba(0,0,0,.12);
  + }
```

- P98（誤植）

```diff
- + <h4>todo list</ht>
+ + <h4>todo list</h4>
```

- P105（脱字）

```
誤: 各タスクのステータスの変更がまだできいないので、これを変更できるように
正: 各タスクのステータスの変更がまだできていないので、これを変更できるように
```

- P110, 112（誤植）

P110 の `③では、〜` にて完了タスクのボタンの非活性化について説明しておりますが、この時点ではボタンの非活性化は行っておらず、また `state.hasDoneTodo` のパラメーターも存在しておりませんでした。

同様に P112 の `一括削除のボタンは3で対象のtodoが存在しなければ非活性に〜` の記述も誤植となります。ただし、`⑦でスタイルを調整しています。` の記述については正しい記述となります。

- P112（誤植）

一点目：
`⑤では、〜` は、P110 の `⑤では、〜` が正しく、書籍のものは削除し忘れとなります。

二点目：
以下の誤植です。

```diff
誤: ⑤では、updateHasDoneTodo という名前で、
正: ⑤では、checkDoneTodo という名前で、
```

- P125（誤植）

```diff
onBeforeMount(props, state) {
  state.todoList = props.todoList
- this.updateHasDoneTodo()
+ this.checkDoneTodo()
  this.obs = observable(this)
},
```
