---
# try also 'default' to start simple
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
---

# ヤマアラシのインターフェース

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---

# semantics / syntax

- syntax

処理系が正しいコードとして解釈可能な文字や記号の並べ方、単語や文の組み合わせ方などの規則の総体である。プログラミング言語の場合、例えば「複数の文を並べる場合はセミコロンで区切る」「変数は使用前に型と変数名を宣言する」などがシンタックスにあたる。


- semantics

プログラムが持つ「意味」のこと。
プログラミング言語やマークアップ言語などのコンピュータ言語の分野で、あるデータやコードにより記述者が表そうとした意味や意図、内容のこと。

（IT用語辞典 https://e-words.jp/ より。）




（あたりまえすぎてとりあげるほどでもないようなきが...（小声））

<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/guide/syntax#embedded-styles
-->

---

# 主張つよめのsemantics

あらゆるプログラムはsemantics的一面をもつのは自明であって、
それを敢えて主張する必要はない気もするが、
身近なところでも名前から主張してくる輩semanticsがいる。

- semver(semantic versioning)
https://semver.org/lang/ja/

- semantic web
https://ja.wikipedia.org/wiki/%E3%82%BB%E3%83%9E%E3%83%B3%E3%83%86%E3%82%A3%E3%83%83%E3%82%AF%E3%83%BB%E3%82%A6%E3%82%A7%E3%83%96

- semantic UI
https://github.com/Semantic-Org/Semantic-UI

おまけ
- semantic segmentation
各ピクセルをその意味（周辺のピクセルの情報）に基づいて、カテゴリ分類する手法（...らしい）


わかるけど、そんな「我こそがセマンティック！」みたいに言う？😅

命題、なぜそんなにイキれるのか？

---

# 思想つよめのsemantics

それぞれの思想からぽいところを抜き出してみる。

- semver

>バージョンナンバーは依存性の管理において正式な仕様書による取り決めが必要であり、
>名前と正確な定義を与えることよって、ソフトウェアにおいて、意図がユーザーに対して伝わりやすくなる。
>一度、これらの意図を正確にしてしまえば、柔軟な依存性の仕様を作ることが可能。

→　ちゃきっと依存性管理するために、かっちり定義して、他のプログラムとかユーザーとかに意図を伝わりやすくするよ。

- semantic web

>Webサイト上の情報などに意味(semantics)を持たせることで、コンピュータが、より豊富で正確な情報を分析・整理・再利用・提供できるようになることを目指す。

>セマンティック・ウェブの目的はウェブページの閲覧という行為に、データの交換の側面に加えて意味の疎通を付け加えることにある。

- semantics UI
> The goal of Semantic UI is to narrow the divide between how we create meaning personally, through language, and how we construct meaning for computers.
セマンティックUIの目標は、言語を介して個人的に意味を作成する方法と、コンピューターの意味を構築する方法との間の境界を狭めることです。(google翻訳)

(semantic UIの昔のバージョンの開発者用ページから引用、今もそうかは不明、でもたぶんそう)


---

まとめると、

**「送り手（だいたい開発者）が渡す意味を、受け手（人間やコンピュータ）にもっとガンガン伝わるようにしようぜ...！」**

ってこと？



<br/>



(あたりまえじゃないの？)

→　逆に当たり前じゃなかったので、この思想が蔓延ったのでは？

> Many programming languages treat logical and mathematical purity as their primary objectives, often ignoring that most of their human counterparts will never reach a zen like purely computational understanding of phenomenon in concordance with the machines they program.多くのプログラミング言語は、論理的および数学的純粋さを主要な目的として扱い、人間の対応する言語のほとんどが、プログラミングするマシンと一致する現象の純粋な計算による理解のように禅に到達することは決してないことをしばしば無視します。（google翻訳）

先述のsemantic ui から引用。つよめなので話半分。
人間とコンピュータは死んでもわかりあえんということが多分書いてあります。わかりあいたいのに...ぴえん😢

ヤマアラシのジレンマ。

---

さらにこう書いてあります。

> Semantic UI is built around a very different premise, that the real bottleneck in computer programming are humans, and that the best way to advance the web isn't solely providing better institutions for learning programming, or even making more refined tools for existing programmers, but more importantly removing the technical barriers that separate programmatic meaning from human meaning.セマンティックUIは非常に異なる前提に基づいて構築されており、コンピュータープログラミングの本当のボトルネックは人間であり、Webを進歩させる最善の方法は、プログラミングを学習するためのより良い機関を提供することだけではなく、既存のプログラマーのためにより洗練されたツールを作成することです。しかし、もっと重要なことは、プログラムの意味と人間の意味を分ける技術的な障壁を取り除くことです。(google翻訳)

人間とコンピュータがわかり合えないのは圧倒的に人間が悪いし、プログラミングを真面目に学習したところで到底無理。
だが心配するな、俺たちが最高のツールを作り、コンピュータと人間とのインターフェースになってやる。

みたいなことを言っていると思います。

これは、例示した他のライブラリも含めて、全員に共通する矜持(きょうじ)な気が。

**「送り手（だいたい開発者）が渡す意味を、受け手（人間やコンピュータ）にもっとガンガン伝わるようにしようぜ...！」**

**「でもこいつらはどうせわかり合えないから、二者間のインターフェースとして、俺たちが責任もってやろうぜ...!」**

---

# さいごに


semantics勢の個人的にすきなところは、

つよめの矜持をもっていることでなく、

送り手と受け手をヤマアラシとして見捨てることで、インターフェースとしての役割タスクを整理して解決した、しようとしたこと。

サービス等に活かせたらいいなあ🙄

<br/>
<br/>
<br/>


ありがとうございました。
---