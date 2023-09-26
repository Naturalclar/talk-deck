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

---

#### Lexical の利点

- 見た目が無い
- Plugin を宣言的に書ける
- コンテンツは AST で処理される

---

#### Lexical の特徴

- React
- core ライブラリ自体は js

Note:
core ライブラリ自体は js なので React 以外のフレームワークとも併用して使えます。
