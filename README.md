# devcontainer-snippets
VSCode の Remote Containers の定義ファイルのスニペット

## 使い方
1. Remote Containers を使用するリポジトリのトップに `.devcontainer` ディレクトリを作成する
1. `.devcontainer` 配下に、このリポジトリにある Remote Containers の定義ファイルをコピー
1. Remote Containers を使用するリポジトリを VSCode で開く
1. リモートエクスプローラーの `+` ボタンをクリックして `Open Current Folder in Container` を選択

## devcontainer.json Tips

### マウントモードを delegated にしてコンテナの書き込み速度を優先する

デフォルト設定では コンテナ ⇄ ホストのボリューム同期の整合性が厳密であるため、コンテナのファイル書き込み速度が遅くなる。
マウントモードを delegated（コンテナの書き込み速度を優先）に設定することで、コンテナのファイル書き込み速度が向上する。

```json
"remote.containers.workspaceMountConsistency": "delegated",
```

### コンテナが作成された時に依存関係のインストールをする

Remote Container でフォルダを開いたときにすぐに開発ができるように、コンテナが作成された時に依存関係のインストールをするといい。

```json
"postCreateCommand": "npm install"
```
