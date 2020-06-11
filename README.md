# devcontainer-snippets
VSCode の Remote Containers の定義ファイルのスニペット

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
