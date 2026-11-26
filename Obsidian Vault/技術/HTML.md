**11/19**
１ページの区画を作るタグがある
<header>：ページ上部。サイト名やメニュー
<nav>：ページ内の移動メニュー
<main>：ページの中心となる内容
<section>：検索欄や作品一覧など、内容のまとまり
<article>：作品カードなど、それだけで意味が通じる内容
<footer>：ページ下部


２idはページの内リンクにも使う
href=`"#anime-list"` を押すと、`id="anime-list"` の場所に移動する。

３HTMLファイルの設定
ファイルは `.html` の拡張子で保存


**11/26**

１CSSはページの見た目を指定する

HTMLがページの内容や区画を作り、CSSが色や大きさ、並び方を整える。

CSSはHTMLの`<head>`内にある`<style>`タグに書く。

<style>
  body {
    background: #101116;
    color: white;
  }
</style>

２CSSの書き方
`body`がセレクター、`color`がプロパティ、`white`が値。`body`に表示する文字を白くする指定。

セレクター {
  プロパティ: 値;
}


３classで指定する
HTMLの`class`とCSSのセレクターをつなげて、特定の区画にデザインを指定できる。
<div class="anime-card">作品カード</div>
.anime-card {
  background: #191b22;
  border-radius: 14px;
}
CSSでは、class名の前に`.`を付ける。

４要素の並び方を指定する
`display: flex`は中身を横並びにする。
`display: grid`は中身を格子状に並べる。作品カードの一覧に使った。
.anime-list {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
}

５マウスを重ねた時の見た目
`:hover`を使うと、マウスを重ねたときのデザインを指定できる。
.anime-card:hover {
  border-color: purple;
}

６画面のサイズに合わせて調整する
`@media`を使うと、スマートフォンなど画面が小さいときだけ別のデザインにできる。
@media (max-width: 600px) {
  .search-row {
    flex-direction: column;
  }
}
この例では、画面幅が600px以下のときに検索欄を縦並びにする。

７色を変数にしてまとめる
`:root`に色を登録すると、複数の場所で同じ色を使いやすい。
:root {
  --purple: #a88bff;
}

button {
  background: var(--purple);
}