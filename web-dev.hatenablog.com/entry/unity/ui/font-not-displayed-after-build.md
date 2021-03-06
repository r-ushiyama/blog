---
Title: Unity UI：ビルド後に文字が表示されない
Category:
- Unity
Date: 2019-06-10T06:00:00+09:00
URL: https://web-dev.hatenablog.com/entry/unity/ui/font-not-displayed-after-build
EditURL: https://blog.hatena.ne.jp/mamorums/web-dev.hatenablog.com/atom/entry/17680117127183607962
---

Unity の開発環境でゲームを起動していると、ビルド後に UI Text の文字が表示されなくなることがありました。これから詳細と対応方法について書いていきます。

※ Unity 2018.4.0f1 で動作確認しました。


## 画面イメージ
再生ボタンで起動すると、以下のようになりました。

### ビルド前
[f:id:mamorums:20190605141023p:plain]

### ビルド後
[f:id:mamorums:20190605141038p:plain]


## 原因
原因不明ですが、フォントを変更したら発生するようになりました。デフォルトの Arial だと発生してませんでした。

あとは、

- 背景色：黒
- 文字色：白

といったことにも起因しているかもしれません。

ビルド後に UI Text のインスペクタを見ると、色が黒になっていました。文字が黒だと影響受けないのかもしれません。


## 対応方法
ビルド後にフォントファイルを `Reimport` すると、フォントが表示されるようになりました。

フォントファイルを右クリックすると、

[f:id:mamorums:20190605141119p:plain]

`Reimport` できます。


## 補足
以下の操作後にも、フォントが表示されました。

- Unity（開発環境）を再起動する。
- 変更を保存する。

自分の場合、上書き保存とかをしてもフォントの元の色は変わりませんでした。ビルド後に一時的になってしまうようです。
