---
title: 今日から始まるぞ。ブログ
dalte: 2019-09-30T01:00:00+09:00

---
やぱり、長い時間でパソコン関する技術はやっていなかったので、このブログ作成したは多少手数があるだ。

次は、ブログ作成の手順を紹介していきます。

## プロバイダの選ぶ、[Hugo](https://gohugo.io/ "Hugo")

かつて [Ghost](https://ghost.org/) を利用したんだけど、いろいろな問題が発生しました。

テーマは少ないし、動的セーバーを必要し、`CJK-Languages` サーポートできないし。その様子を見るだけで、微妙な異物を出てきましたが、それでやめてほうがいいと思いました。

自分のはmacOS 環境だから、[Homebrew](https://brew.sh/ "Homebrew") でインストールしよう。

    brew install hugo

[Homebrew](https://brew.sh/ "Homebrew") を持っていない方は、下のコマンドを実行してください

    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

## サイトを作る

文章を打ち込み前に、もうひとつことを忘れないでください。それはベースとしたサイトです、これも簡単。

    hugo new site [site name]

`[site name]`とは、このサイトのネームです。どんなネームでも良い。

## 記事を発表する

いよいよ始まります。

まず、サイトのディレクトリに移動します。

    cd [site name] //先に作ったサイトネーム

例えば、`はじめのブログ`をタイトルとして扱う際は。

    hugo new posts/hajimenoburogu.md

`hajimenoburogu`のファイルネームは、URLの中に表示されるので、ローマ字とより英語方がいいと思います。

こういう風になります。

    ---
    title: "hajimenoburogu"
    date: 2019-09-29T00:00:00+09:00
    draft: true
    ---

`title` は、記事のタイトルです。`はじめのブログ`を入れ替えるのもできます。

`draft: true` は、未公開になるので、公開する際は `false` にする

### ローカルサーバで確認

## Github Pagesを利用する