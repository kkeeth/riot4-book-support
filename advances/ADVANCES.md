# ADVANCES 発展内容

### ▼開発環境構築用ライブラリ `create-riot` がリリース

Riot.js で開発環境を用意したい場合、[公式のサンプル集](https://github.com/riot/examples) から各バンドラを利用したディレクトリをコピーするか、一から手で作っていく必要がありました。

また、各フレームワーク・ライブラリには公式で CLI が用意され、その CLI を利用するとある程度自分たちの望む開発環境が対話式で用意できるようになっておりましたが、本書執筆時点では Riot.js にはそのようなツールは有りませんでした。

しかし、__出版と同時に__ [create-riot](https://www.npmjs.com/package/create-riot) というツールが開発され、npm に公開されました（もっと早く出てほしかった）。。。

使い方については手前味噌ですが、私が Qiita に投稿した記事がありますので、参考までに見ていただけますと幸いです。

[Riot.js の開発環境構築に新たな革命が！](https://qiita.com/clown0082/items/9c908309c2031f398baf)

### ▼ `riot` のメジャーアップデート `v5` がリリース

2020年10月16日 1:53(JST) に、メジャーアップデートが行われ、正式に version5 がリリースされました。

https://github.com/riot/riot/releases/tag/v5.0.0

今回の変更点を日本語に訳したものが以下となります。

---
このリリースは完全に下位互換性がありますので、`riot@5.0.0` と一緒に `@riotjs/compiler@5.0.0` をアップデートするようにしてください。Riot.js のエコーシステムツールはすべて、メジャーリリースのアップデートを必要とせずに、期待通りに動作し続けるはずです。

__変更点__

* 内部の [domdiff](https://github.com/WebReflection/domdiff) レンダリングエンジンを [udomdiff](https://github.com/WebReflection/udomdiff) のフォークで置き換える
* レンダリングパフォーマンスの向上
* ライブラリサイズの改善（-1kb）
* Riot.js の副作用の改善。ES2015 のエクスポートもサポートしているので、完全にツリーシェイクが可能
* [#2878](https://github.com/riot/riot/issues/2878) の修正 式内のブラウザグローバル変数は `window` プロパティとしてのみ利用できるように修正

  __破壊的変更__ 旧 `{ location.href }` 新 `{ window.location.href }`
