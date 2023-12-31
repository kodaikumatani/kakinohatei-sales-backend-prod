# JAianba-ERP-Backend
JAinaba ERP は、JA鳥取イナバグループの直売所に商品を出荷している生産者向けの売上管理システムです。  
Backendでは、APIとBatchを提供します。

## Overview
- [ER図](./docs/er_diagram.md)
- [ユースケース図](./docs/usecase_diagram.md)
- [シーケンス図](./docs/er_diagram.md)

JAinaba ERP は、JA 鳥取イナバグループの直売所に商品を出荷している生産者向けの売上管理システムです.  
API と Batch を提供します。

## Getting Start

開発には [Laravel Sail](https://readouble.com/laravel/9.x/ja/sail.html) を使用します.

```
# Compoer依存関係のインストール
docker run --rm \
    -u "$(id -u):$(id -g)" \
    -v "$(pwd):/var/www/html" \
    -w /var/www/html \
    laravelsail/php82-composer:latest \
    composer install --ignore-platform-reqs

# Laravel SetUp
cp .env.example .env
```

## Command

```
./vendor/bin/sail up -d                 Sailの立ち上げ
./vendor/bin/sail php artisan key:generate
./vendor/bin/sail php artisan migrate   マイグレーションの実行
```

## 構文チェック&静的解析

### Remote に Push する前に実行してください

```
# PHPStan
./vendor/bin/phpstan analyse -c phpstan.neon --memory-limit=2G

# Laravel Pint
./vendor/bin/pint
```

## .editorconfig

[`.editorconfig`](/.editorconfig) でインデントやスペースのルールを定義し、書くときにブレが生じないようにしています.
.editorconfig をサポートしている IDE やエディタ、拡張機能の導入をおすすめします.

### Visual Studio Code

拡張機能 [EditorConfig for VS Code](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)

## コミットメッセージルール

#### Prefix を先頭に付けてください

-   feat: 新しい機能
-   fix: バグの修正
-   docs: ドキュメントのみの変更
-   style: 空白、フォーマット、セミコロン追加など
-   refactor: 仕様に影響がないコード改善(リファクタ)
-   perf: パフォーマンス向上関連
-   test: テスト関連
-   chore: ビルド、補助ツール、ライブラリ関連
