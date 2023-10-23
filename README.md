# wp-env test

## 起動手順

プロジェクトルートに`auth.json` を作成し username キーに ACF Pro のライセンスキーを指定

```json
{
  "http-basic": {
    "connect.advancedcustomfields.com": {
      "username": "{ACF_PRO_KEY}",
      "password": "https://camp4.jp/"
    }
  }
}
```

wp-env など依存モジュールをインストール

```sh
npm ci
```

wp-env を起動

```sh
npm run wp-env start
```

composer のモジュールをインストール

```sh
npm run composer install
```

## 備考

他のプロジェクトとポート番号が重複する場合は `.wp-env.override.json`を追加し設定を上書きする

例）

```json
{
  "port": 4440,
  "env": {
    "tests": {
      "port": 4441
    }
  }
}
```

### リソース

- [@wordpress/env](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-env/)
