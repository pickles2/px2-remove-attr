pickles2/px2-remove-attr
=========

px2-remove-attr は、Pickles 2 に、HTMLドキュメントから指定した属性を削除する機能を提供します。
この機能はパブリッシュ実行時に働きます。プレビュー時には作用しません。


## Usage - 使い方

### 1. Pickles2 をセットアップ

### 2. composer.json に追記

```json
{
    "require": {
        "pickles2/px2-remove-attr": "^2.0.0"
    }
}
```

### 3. composer を更新

```
$ composer update
```

### 4. px-files/config.php に追加

`$conf->funcs->processor->html` にAPI設定を追加します。

```php
<?php

$conf->funcs->processor->html = [
    // HTML属性を削除する
    'tomk79\pickles2\remove_attr\main::exec('.json_encode(array(
        "attrs"=>array(
            'data-remove-test',
            'data-remove-2-test',
        ) ,
    )).')' ,
];
```

HTMLタグから、`attrs` に指定した属性を削除します(タグごと削除するのではなく、属性だけ削除します)。
`attrs` は配列です。複数の属性を指定できます。


## 開発者向け情報 - for Developer

### テスト - Test

```
$ cd {$documentRoot}
$ composer test
```

## 更新履歴 - Change log

### pickles2/px2-remove-attr v2.1.1 (2023年2月11日)

- 内部コードの細かい修正。

### pickles2/px2-remove-attr v2.1.0 (2022年1月8日)

- サポートするPHPのバージョンを `>=7.3.0` に変更。
- PHP 8.1 に対応した。

### pickles2/px2-remove-attr v2.0.3 (2019年9月10日)

- PHP 7.3系 で起きるエラーを修正した。

### pickles2/px2-remove-attr v2.0.2 (2018年8月30日)

- 細かい不具合の修正。

### pickles2/px2-remove-attr v2.0.1 (2018年3月16日)

- 0バイトのコンテンツがある場合に Fatal Error が起きる不具合を修正した。

### pickles2/px2-remove-attr v2.0.0 (2016年2月12日)

- initial release.

## ライセンス - License

Copyright (c)2001-2023 Tomoya Koyanagi, and Pickles 2 Project<br />
MIT License https://opensource.org/licenses/mit-license.php


## 作者 - Author

- Tomoya Koyanagi <tomk79@gmail.com>
- website: <https://www.pxt.jp/>
- Twitter: @tomk79 <https://twitter.com/tomk79/>
