# デプロイテストアプリケーション

Spring Bootを使用したシンプルなWebアプリケーションです。デプロイテスト用に作成されています。

## 技術スタック

- **言語**: Java 17
- **フレームワーク**: Spring Boot 3.2.0
- **ビルドツール**: Maven
- **テンプレートエンジン**: Thymeleaf

## 機能

- ホームページ表示
- ヘルスチェックAPI
- 挨拶API

## ビルド方法

```bash
mvn clean package
```

## 実行方法

### Maven経由で実行

```bash
mvn spring-boot:run
```

### JARファイルから実行

```bash
java -jar target/deploy-test-app-1.0.0.jar
```

## アクセス方法

アプリケーション起動後、以下のURLにアクセスできます：

- **ホームページ**: http://localhost:8080/
- **ヘルスチェック**: http://localhost:8080/api/health
- **挨拶API**: http://localhost:8080/api/hello?name=太郎

## エンドポイント

### GET /

ホームページを表示します。

### GET /api/health

アプリケーションのヘルスステータスをJSON形式で返します。

**レスポンス例:**
```json
{
  "status": "UP",
  "timestamp": "2024-01-01 12:00:00",
  "message": "アプリケーションは正常に動作しています"
}
```

### GET /api/hello

挨拶メッセージをJSON形式で返します。

**パラメータ:**
- `name` (オプション): 挨拶する相手の名前（デフォルト: "World"）

**レスポンス例:**
```json
{
  "message": "Hello, 太郎!",
  "timestamp": "2024-01-01 12:00:00"
}
```

## ポート番号の変更

`src/main/resources/application.properties` ファイルの `server.port` を変更することで、ポート番号を変更できます。

## 注意事項

- このアプリケーションはデータベースを使用しません
- デプロイテスト用のシンプルなアプリケーションです

