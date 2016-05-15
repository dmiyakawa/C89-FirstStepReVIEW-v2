# C89-FirstStepReVIEW-v2 test

## 本を読むには？

### 電子書籍として閲覧する場合

https://techbooster.booth.pm/
でPDF版の販売予定があります

### 物理本がほしい場合

http://shop.comiczin.jp/products/list.php?category_id=4911
ComicZinさんにて委託分があります

## この本のビルドの仕方

細かい準備(TeX入れたり)は[FirstStepReVIEW](https://github.com/TechBooster/FirstStepReVIEW)に準じます。

TeXの導入をしない場合でもHTML出力は可能です。Dockerコンテナでビルドすることもできます。

### PDF出力する

rbenvやnodebrewを利用してRubyやNode.jsの準備をしている前提です。
もしそうではない場合、適宜sudoを補うこと。
Node.jsは4.x系以上が必須です。

graphvizを使ったのでbrew install graphvizとかが必要かもしれません。

```
$ gem install bundler
$ git clone git@github.com:TechBooster/C89-FirstStepReVIEW-v2.git
$ cd C89-FirstStepReVIEW-v2
$ npm install
$ npm run pdf
```

### Dockerを使う

TeXの環境構築が困難な場合、一式セットアップ済みの[dockerイメージ](https://registry.hub.docker.com/u/vvakame/review/)を用意してあるので使ってください。
Dockerがうまく動くようになっている場合、以下のコマンドで細かい準備なしにビルドを行うことができます。

```
$ docker pull vvakame/review
$ ./build-in-docker.sh
```

### HTML出力

`npm run web` を実行すると、`publish/`ディレクトリ以下に公開用HTMLファイルおよびcss,画像を出力します。
