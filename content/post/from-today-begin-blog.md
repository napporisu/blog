---
title: 今日から始めるぞ。ブログ
date: 2019-09-29T16:00:00.000+00:00
toc: false
images: []
tags: []

---
やっぱり、長い時間パソコンに関する仕事はやっていなかったので、このブログ作成したは多少手間がかかった。

まずは、ブログ作成の手順を紹介していきます。

## プロバイダを選ぶ、[Hugo](https://gohugo.io/ "Hugo")

かつて [Ghost](https://ghost.org/) を利用したんだけど、いろいろな問題が発生しました。

テーマは少ないし、動的セーバーを必要とし、`CJK-Languages` をサーポートできないし。その様子を見るだけで、奇妙ことを起きたんので、それでやめたほうがいいと思いました。

自分のはmacOS 環境だから、[Homebrew](https://brew.sh/ "Homebrew") でインストールします。

    brew install hugo

[Homebrew](https://brew.sh/ "Homebrew") を持っていない方は、下のコマンドを実行してください

    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

## サイトを作る

文章を打ち込む前に、もうひとつ忘れないでください。それはベースとするサイトの作成、これも簡単。

    hugo new site [site name]

`[site name]`とは、このサイトのネームです。どんなネームでも良い。

## 記事を発表

まず、サイトのディレクトリに移動します。

    cd [site name] //先に作ったサイトネーム

例えば、`はじめのブログ`をタイトルとする場合。

    hugo new posts/hajimenoburogu.md

`hajimenoburogu`のファイルネームは、URLの中に表示されるので、ひらがなよりローマ字ほうがいいと思います。

するとこういう風になります。

    ---
    title: "hajimenoburogu"
    date: 2019-09-29T00:00:00+09:00
    draft: true
    ---

* `title` は、記事のタイトルです。`はじめのブログ`を入れ替えるのもできます。
* `draft: true` は、未公開になるので、公開する際は `false` にします。

## ローカルサーバで確認

ここまでできたら、ブログのサイトを見てみたいでしょう？ローカルサーバもプレビューもできる。

    hugo server -D

* `-D` をつけると`draft: true` の記事もプレビューできる
* [http://localhost:1313/](http://localhost:1313/) でチェックします

確認してオッケーだったら、ウェブサイトとして公開しましょう

## Github Pagesで利用

[Github](https://github.com/ "Github")のアカウントを作成するの条件はただ一つ、メールアドバイスだけで十分。

`Github Pages` 用のレポジトリは、\[`username].github.io` のようなルールを絶対に守ります。もちろん、`[username]` は Github アカウントの名です。

`hugo` コマンドでビルドすると、`public` に公開用ファイルが作成される。そして、中身を全部pushしよう。

    hugo
    cd public
    git add .
    git commit -m 'initial commit'
    git remote add origin git@github.com:[username]/[username].github.io.git
    git push -u origin master

これでは、`[username].github.io` まだ見えないですが、github 自身もプログラムを実行するのには時間がかかりますので、数分を待ってください。

## おわり

やっぱり、日本語でこの記事を書くのは、無理やり過ぎでした。