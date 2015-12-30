tomk79/px2-remove-attr
=========

px2-remove-attr は、Pickles 2 に、HTMLドキュメントから指定した属性を削除する機能を提供します。


## Usage - 使い方

### 1. Pickles2 をセットアップ

### 2. composer.json に追記

```
{
    "repositories": [
        {
            "type": "git",
            "url": "https://github.com/tomk79/px2-remove-attr.git"
        }
    ],
    "require": {
        "tomk79/px2-remove-attr": "dev-master"
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
    'tomk79\pickles2\remove_attr\main::exec()' ,
];
```


## 開発者向け情報 - for Developer

### テスト - Test

```
$ cd {$documentRoot}
$ composer test
```
