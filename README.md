# ip.kyms.jp

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PHP](https://img.shields.io/badge/PHP-777BB4?style=flat&logo=php&logoColor=white)](https://php.net/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)](https://html.spec.whatwg.org/)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)](https://www.w3.org/Style/CSS/)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Website](https://img.shields.io/website?url=https%3A//ip.kyms.jp)](https://ip.kyms.jp)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=flat&logo=github&logoColor=white)](https://github.com/yama/iptool)

シンプルで使いやすい IP アドレス確認サービスです。

## 概要

ip.kyms.jp は、現在の IP アドレスを簡単に確認できるウェブサービスです。ブラウザからのアクセスでは詳細な情報と共に表示し、CLI ツール（curl、wget など）からのアクセスでは IP アドレスのみをプレーンテキストで返します。

## 特徴

- **シンプルなインターフェース**: 分かりやすく見やすいデザイン
- **詳細情報表示**: IP アドレス、ブラウザ情報、OS 情報、画面解像度を表示
- **CLI 対応**: curl や wget からのアクセスで IP アドレスのみを取得可能
- **ワンクリックコピー**: IP アドレスをクリックするだけでクリップボードにコピー
- **レスポンシブデザイン**: モバイルデバイスにも対応

## 使用方法

### ブラウザからのアクセス

[https://ip.kyms.jp](https://ip.kyms.jp) にアクセスすると、以下の情報が表示されます：

- あなたの IP アドレス
- ブラウザ情報
- OS 情報
- 画面解像度

### CLI からのアクセス

```bash
# curl を使用
curl https://ip.kyms.jp

# wget を使用
wget -qO- ip.kyms.jp
```

CLI からのアクセスでは、IP アドレスのみがプレーンテキストで返されます。

## 技術仕様

- **言語**: PHP
- **フロントエンド**: HTML5、CSS3、JavaScript
- **依存関係**: なし（標準的な PHP 環境で動作）
- **ブラウザサポート**: モダンブラウザ（User-Agent Client Hints API 対応）

## ファイル構造

```text
public_html/
└── index.php    # メインアプリケーションファイル
```

## 機能詳細

### IP アドレス検出

`$_SERVER['REMOTE_ADDR']` を使用してクライアントの IP アドレスを取得します。

### CLI 判定

User-Agent ヘッダーと Accept ヘッダーを解析して、CLI ツールからのアクセスかどうかを判定：

- `curl` または `wget` が User-Agent に含まれる
- Accept ヘッダーが `text/plain` の場合

### ブラウザ・OS 情報取得

- **モダンブラウザ**: User-Agent Client Hints API を使用
- **フォールバック**: 従来の User-Agent 文字列解析

## ライセンス

このプロジェクトは MIT ライセンスの下で公開されています。

## 作者

yamamoto ([@yama](https://github.com/yama))

## リンク

- **ウェブサイト**: [https://kyms.jp](https://kyms.jp)
