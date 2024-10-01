### OpenAPI の仕様書から指定した Postman のコレクションを自動更新する Docker イメージのサンプル Repository

#### イメージ（Docker Hub）

https://hub.docker.com/r/fukuemon/postman_collection_update

#### 使い方（Zenn）

[OpenAPI の仕様書から指定した Postman のコレクションを自動更新する Docker イメージを作ったので紹介します](https://zenn.dev/fukuemon/articles/1a918a5ade7cf7)

1. `.env`ファイルに下記の値を定義

```
POSTMAN_API_KEY=
POSTMAN_COLLECTION_ID=
OPENAPI_FILE_PATH=
PATHPARAMETERS=
```

| 環境変数名        | 説明                                                             | 例                                                                                            |
| ----------------- | ---------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| OPENAPI_FILE_PATH | マウント先の OpenAPI 仕様書の path （**/忘れずに**）             | `./internal/docs/openapi.json:/openapi.json`とした場合<br> `OPENAPI_FILE_PATH=/openapi.json ` |
| PATHPARAMETERS    | Postman の変数に置き換えたい PathParameter（半角スペース区切り） | `PATHPARAMETERS=facility_id position_id department_id team_id position_id`                    |

2. 実行

```
docker compose up
```
