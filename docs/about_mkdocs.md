# MkDocs について

このドキュメントは, [mkdocs.org](https://www.mkdocs.org) と 派生の [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) で生成されています.

公式ドキュメントは,

- [mkdocs.org](https://www.mkdocs.org)
- [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)

を参照してください.

!!! Warning
    `Material for Mkdocs version 5.x` では, 日本語検索に問題があったので `4.x` バージョンを使用しています. 公式ドキュメントは, バージョン `5.x` に準拠しているので, サンプルの設定をそのまま使用すると適切に動作しない場合があります.

    問題がある場合は, [Upgrading to 5.x - Material for MkDocs](https://squidfunk.github.io/mkdocs-material/releases/5/#changes-to-mkdocsyml) を参考にしてみてください.

以下は簡単なチュートリアルです.

## 環境構築とサーバーの起動

[Python3系](https://www.python.org/)とパッケージマネージャの[Pipenv](https://pipenv-ja.readthedocs.io/ja/translate-ja/)が必要です.

``` sh
$ pip install pipenv  # pipenv ガインストールされてなければ取得する
$ pipenv install
$ pipenv run dev
INFO    -  Building documentation... 
INFO    -  Cleaning site directory 
INFO    -  Documentation built in 0.59 seconds 
[I 200608 21:55:58 server:334] Serving on http://127.0.0.1:8000
INFO    -  Serving on http://127.0.0.1:8000
[I 200608 21:55:58 handlers:62] Start watching changes
INFO    -  Start watching changes
[I 200608 21:55:58 handlers:64] Start detecting changes
INFO    -  Start detecting changes
```

サーバーが起動し, http://127.0.0.1:8000 からドキュメントを確認できます.

## ディレクトリ構造

ディレクトリ構造は, 以下の通りです.

    mkdocs.yml           # 設定ファイル
    docs/
        index.md         # トップページ
        about_mkdocs.md  # mkdocsについて, このページ
        ...              # その他のドキュメントファイル
    site/                # ビルド先ディレクトリ

!!! Tip
    `docs` 内にディレクトリを配置することで階層化して記事を配置できます.

## ドキュメントのビルド

``` sh
$ pipenv run build
```

`site` ディレクトリに, ビルドされたHTMLソースが設置されます.

!!! Tip
    生成されたソースは, そのまま [GitHub Pages \| Websites for you and your projects, hosted directly from your GitHub repository. Just edit, push, and your changes are live.](https://pages.github.com/) などでホスティングできます.

## 特殊記法

`Mkdocs` では, 通常のマークダウン記法に加えて特殊な記法が使えます.

一部を紹介しますが, 詳しくは公式ドキュメントを参考にしてください.

### 1. サイドコンテンツ

`!!! <keyword>` を使うことで, ブロック化されたサイドコンテンツを表示できます.

``` markdown
!!! Note
    サンプルのノートです.
```

このように書くと,

!!! Note
    サンプルのノートです.

このように表示されます.

`Note` キーワードの他に, 以下のキーワードも使用できます.

- Abstract
- Info
- Tip
- Success
- Question
- Warning
- Failure
- Danger
- Bug
- Example
- Quote

また, `!!! <keyword>` の代わりに `??? <keyword>` を使うことで, 折りたたみ可能なサイドコンテンツを作成できます.

``` markdown
??? Note
    これは折りたたみ可能なノートです。
```

??? Note
    これは折りたたみ可能なノートです。

より詳しくは, [Admonition - Material for MkDocs](https://squidfunk.github.io/mkdocs-material/extensions/admonition/)を参照してください.

### 2. 注釈

`<word>[^<num>]` の記法で, word に注釈をつけることができます.

``` markdown
`Mkdocs` では, markdown[^1] でドキュメントを書くことができます！

[^1]: マークダウンとは, 文書を記述するための軽量マークアップ言語のひとつである。本来はプレーンテキスト形式で手軽に書いた文書からHTMLを生成するために開発されたものである。
```

`Mkdocs` では, markdown[^1] でドキュメントを書くことができます！

[^1]: マークダウンとは, マークダウンとは, 文書を記述するための軽量マークアップ言語のひとつである。本来はプレーンテキスト形式で手軽に書いた文書からHTMLを生成するために開発されたものである。

このように, 注釈が追加されます.

定義された注釈は, ページ下部にまとめられます.

より詳しくは, [Footnotes - Material for MkDocs](https://squidfunk.github.io/mkdocs-material/extensions/footnotes/) を参照してください.

### 3. fontawesome

`:<keyword>:` で, fontawesome を利用できます.

``` markdown
:fa-search:
:fa-plus:
:fa-remove:
```

:fa-search:
:fa-plus:
:fa-remove:

このように, アイコンが表示されます.

アイコンは, [Font Awesomeで検索 :fa-search:](https://fontawesome.com/icons?d=gallery&q=) しましょう.

### 4. チェックリスト

チェックリストにも対応しています.

``` markdown
**To Do List**

- [x] やること1
- [ ] やること2
```

**To Do List**

- [x] やること1
- [ ] やること2

## カスタマイズ

他にも, UML図をかけるようにしたり, 数学関数の記述を可能にしたりと, 用途に応じて拡張できます.

基本的には,

- mkdocs.yml
- css/*.css
- js/*.js

を編集することで, 拡張します.

詳しくは,

- [Customization - Material for MkDocs](https://squidfunk.github.io/mkdocs-material/customization/)
- [MkDocsによるドキュメント作成 - Qiita](https://qiita.com/mebiusbox2/items/a61d42878266af969e3c)

この辺りが参考になると思います.
