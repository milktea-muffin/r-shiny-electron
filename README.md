# r-shiny-electron

Rのshinyを起動させるElectronアプリのテンプレート

## フォルダ構成

最終的なフォルダ構成

```sh
r-shiny-electron
    # Electron関連
    |- main.js - Rを起動するメインプログラム
    |- renderer.js - 実際のところ必要なのかよくわからない
    |- package.json - 設定ファイル
    |- package-lock.json
    # R, shiny関連
    |- R-Portable-Win - R-Portableをダウンロードする
    |- R-Portable-Mac - どこで入手できるか分からないけど参考にしたGithubレポジトリにある
    |- app.R - shinyを起動するRプログラム
    |- shiny - shinyプログラム
        |- global.R- パッケージのロード、ui.R, server.Rの共通の変数/関数定義など
        |- server.R - 全画面で共通の関数など
        |- ui.R - 全体の枠などの基本レイアウト
        |- setver_template.R - 個々の画面のserver.Rのテンプレート
        |- ui_template.R - 個々の画面のui.Rのテンプレート
    |- www - shinyのカスタムcss, jsを保存するフォルダ
        |- custom.css
        |- custom.js
```

## 使い方

このレポジトリをクローンし、nodeモジュールをインストールする。さらに同フォルダにR-Portableをダウンロードし、R-Portableに必要なライブラリをインストールする。

```bash
# Clone this repository
git clone https://github.com/milktea-muffin/r-shiny-electron.git
# Install Electron Packager (if first time)
npm install electron-packager -g
# Go into the repository
cd r-shiny-electron
# Install dependencies
npm install
# Run the app
npm start
# Build the Executable/App
cd electron-quick-start
npm run package-win
OR
npm run package-mac
```

## 参考にしたGithubレポジトリ

- [ColumbusCollaboratory/electron-quick-start](https://github.com/ColumbusCollaboratory/electron-quick-start) - R-Portableを使用したRのshinyが起動するElectronアプリ。主にR-Portable-Win/Macとの連携や起動までの手順を参考にした。
- [romanhaa/Cerebro](https://github.com/romanhaa/Cerebro) - 上記Electronアプリを参考にしたscRNA-seqのViewer。main.jsはこちらの方を参考に作成した。
