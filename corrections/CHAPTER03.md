# CHAPTER 03 はじめての Riot.js でのアプリケーション開発

#### ▼ P92（誤植）

Plunker の preview の URL はソースコードを変更して保存したり別ブラウザで閲覧するなどすると、変更することがあるため、書籍に記述した URL ではデモアプリを確認することができなくなってしまいました。

以下の URL にアクセスしてみてください。

```
誤: https://run.plnkr.co/preview/ck8em6dla001a2a6lbxtc9nbd/
正: https://plnkr.co/plunk/Uoghj8aOznPhxdoQ6GHJ
```

#### ▼ P95（誤植）

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

#### ▼ P98（誤植）

```diff
- + <h4>todo list</ht>
+ + <h4>todo list</h4>
```

#### ▼ P103（誤植）

ソースコード上のイベントハンドラの指定が間違っておりました。

```diff
  + <input
  +   name="todo"
  +   value=""
  +   placeholder="please input task"
- +   oninput={ input }
+ +   onkeyup={ input }
  + />
```

#### ▼ P105（脱字）

```
誤: 各タスクのステータスの変更がまだできいないので、これを変更できるように
正: 各タスクのステータスの変更がまだできていないので、これを変更できるように
```

#### ▼ P110, 112（誤植）

P110 の `③では、〜` にて完了タスクのボタンの非活性化について説明しておりますが、この時点ではボタンの非活性化は行っておらず、また `state.hasDoneTodo` のパラメータも存在しておりませんでした。

同様に P112 の `一括削除のボタンは③で対象のtodoが存在しなければ非活性に〜` の記述も誤植となります。ただし、`⑦でスタイルを調整しています。` の記述については正しい記述となります。

また上記に付随して、ナンバリングが一つずつズレております。

- P110 の `④では` は P109 の ③ に当たります
- P110 の `⑤では` は P109 の ④ に当たります

#### ▼P111（誤植）

文中でいきなり `...newTask` というパラメータが出てきておりますが、こちらのパラメータは後ほど出てくるもので、P111 の時点では以下の記述が正しいものとなります。

```diff
  + const updatedTodoList = [
  +   ...this.state.todoList,
  +
  +   {
  +     id: this.state.nextId + 1,
- +     ...newTask
+ +     title: e.target.todo.value,
+ +     done: false
  +   }
  + ]
    this.update({
  +   hasDoneTodo: this.checkDoneTodo(updatedTodoList),
  -   todoList: [
  -     ...this.state.todoList,
  -     {
  -       id: this.state.nextId + 1,
- -       ...newTask
+ -       title: e.target.todo.value,
+ -       done: false
  -     }
  -   ],
```

#### ▼ P112（誤植）

一点目：
P110 の `⑤では、〜` が正しく、P112 のものは削除し忘れとなります。

二点目：
本文中の `updateHasDoneTodo` というメソッドは存在せず、`checkDoneTodo` が正しいメソッド名となります。

```diff
誤: ⑤では、updateHasDoneTodo という名前で、
正: ⑤では、checkDoneTodo という名前で、
```

三点目：
申し訳ないですが、本文中の `⑤では、〜` の途中からの文言が全て誤植となります。。

```
誤: state の todoList という配列 に対して filter という JavaScript のメソッドを利用して1つひとつ調べ、done となっている todo を抽出しています。その個数を数え、0より大きければ完了しているtodoが存在することを
意味するので、state の hasDoneTodo フラグの値を true に変更しています。
正: 引数の updatedTodoList または state の todoList という配列に対して some という JavaScript のメソッドを利用して一つ一つ調べ、done となっている todo をチェックしています。true の todo が一つでも存在すれば完了
を意味するので true を、一つも存在しなければ false を返しています。
```

#### ▼ P119（誤植）

P111 と同様に `...newTask` の誤植となります。

```diff
  - const updatedTodoList = [
  -   ...this.state.todoList,
  -   {
  -     id: this.state.nextId + 1,
- -     ...newTask
+ -     title: e.target.todo.value,
+ -     done: false
  -   }
  - ]
```

#### ▼ P120（誤植）

P111, P119 と同様に `...newTask` の誤植となります。

```diff
  + const updatedTodoList = [
  +   ...this.state.todoList,
  +   {
  +     id: this.state.nextId + 1,
- +     ...newTask
+ +     title: e.target.todo.value,
+ +     done: false
  +   }
  + ]
```

#### ▼ P123（誤植）

P120 にて追加したコードと、P123 で削除するコードが一致しておりませんでした。

```diff
- - this.update({
- -   todoList: [
- -     ...this.state.todoList,
- -     {
- -       id: this.state.nextId + 1,
- -       title: e.target.todo.value,
- -       done: false
- -     }
- -   ],
- -   nextId: this.state.nextId + 1,
- -   isInput: false,
- -   hasDoneTodo: this.props.checkDoneTodo()
- - })
+ - const updatedTodoList = [
+ -   ...this.state.todoList,
+ -   {
+ -     id: this.state.nextId + 1,
+ -     ...newTask
+ -   }
+ - ]
+ - this.update({
+ -   todoList: updatedTodoList,
+ -   nextId: this.state.nextId + 1,
+ -   isInput: false
+ -   hasDoneTodo: this.props.checkDoneTodo(updatedTodoList),
+ - })
```

#### ▼ P125（誤植）

ソースコード中の updateHasDoneTodo というメソッドは存在せず、checkDoneTodo が正しいメソッド名となります。

```diff
onBeforeMount(props, state) {
  state.todoList = props.todoList
- this.updateHasDoneTodo()
+ this.checkDoneTodo()
  this.obs = observable(this)
},
```

#### ▼ P127（誤植）

冒頭のソースコードの以下の `<button>` タグの変更は特になく、かつ記述が間違っておりました。

```diff
- - <button disabled={ !state.isInput }>
- + <button disabled={ !props.isInput }>
+ <button disabled={ !isInput }>
```

#### ▼ P130（誤植）

todo-list.riot の `deleteTodo` メソッドの中の変数名が間違っておりました。

```diff
- + const filteredTodoList
+ + const updatedTodoList
  +   = this.props.todoList.filter(item => item.id !== todo.id)
  + this.update({
  +   hasDoneTodo: this.checkDoneTodo(updatedTodoList),
  +   todoList: updatedTodoList
  + })
```

#### ▼ P131（誤植）

P130 と同様に、todo-list.riot の `deleteTodo` メソッドの中の変数名が間違っておりました。

```diff
-   const filteredTodoList
+   const updatedTodoList
      = this.props.todoList.filter(item => item.id !== todo.id)
  - this.update({
  -   hasDoneTodo: this.checkDoneTodo(updatedTodoList),
  -   todoList: updatedTodoList
  - })
  + // ⑨
- + this.props.observable.trigger('delete todo', filteredTodoList)}
+ + this.props.observable.trigger('delete todo', updatedTodoList)}
```
