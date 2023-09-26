### Lexical 使ってみたら使い心地が良かったので布教したい！

---

### Lexical とは

<div class="flex justify-center">
<img
src="./assets/lexical.png"
/>

</div>

---

#### Lexical とは

- [Lexical](https://lexical.dev/)
- Meta 社が開発したテキストエディタフレームワーク
- 拡張性、汎用性、パフォーマンスに優れている
- 2022 年注目されてたライブラリの一つ

Note:
2022 年 star 数ランキングみたいなのを知り合いと見てた

---

#### 他のエディタライブラリの難点

他のライブラリ(n=1)

- 見た目が殆ど固定されている
- 可読性に難がある(個人的に)
- 既存の DOM を変換が大変

Note:
案件でサービス内で使う WYSIWYG エディタを開発していた時の話
特定のライブラリには触れない
エディタは Event ベースで処理を行うことが多いので、「このイベントが起きた時これが発生する。」というのを把握していかないといけない
太字にするなどの書体変更に DOM 操作が行われていた。span タグを挿入したりなど。

---

#### Lexical の利点

- 見た目が無い
- Plugin を宣言的に書ける
- コンテンツは AST で処理される

---

#### Lexical の特徴

- 公式が React plugin を提供
- core ライブラリ自体は js
- plugin を楽に追加可能

```sh
bun install lexical @lexical/react
```

Note:
core ライブラリ自体は js なので React 以外のフレームワークとも併用して使えます。

---

#### Lexical Node

```ts
// 簡略化した型

type RootNode {
  children: ParagraphNode[]
}

type ParagraphNode {
  children: TextNode[]
}

type TextNode {
  value: string
  format: Format[]
}

type Format = 'bold' | 'italic' | 'underline'

```

---

#### Lexical での操作

```js
import {
  $getRoot,
  $getSelection,
  $createParagraphNode,
  $createTextNode,
} from "lexical";

// `editor.update` 関数の中で $ から始まるヘルパー関数を呼び出して操作します。
// editor.update の外でこれらの関数を使おうとするとエラーになります
editor.update(() => {
  // EditorState の RootNode を取得
  const root = $getRoot();

  // 現在選択中の Node を取得
  const selection = $getSelection();

  // ParagraphNode を新しく作成
  const paragraphNode = $createParagraphNode();

  // TextNode を新しく作成
  const textNode = $createTextNode("Hello world");

  // ParagraphNode に TextNode を追記
  paragraphNode.append(textNode);

  // RootNode に ParagraphNode を追記
  root.append(paragraphNode);
});
```

---

### 実際に見てみよう

---

### 決して登壇資料が間に合わなかったではないよ

---

### もう一度言うけど決して登壇資料が間に合わな
