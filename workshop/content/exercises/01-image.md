dokcerが実行可能なことを確認します。出力内容にServerとClientが表示されていることを確認してください。

```execute
docker version
```

#### dockerの基本コマンド

- docker run : コンテナを起動
- docker stop : コンテナを停止
- docker ps : コンテナ一覧を表示
- docker pull : コンテナイメージを取得
- docker images : コンテナイメージ一覧を表示
- docker exec : 起動中のコンテナ内でコマンドを実行
- docker attach : コンテナに接続
- docker logs : コンテナのログを表示

#### コンテナイメージの検索とダウンロード

centosという名前のコンテナイメージをdocker registoryに問い合わせます。 一部のイメージはオフィシャルイメージとして提供されています。

```execute
docker search centos
```

pullコマンドにより、CentOSイメージをダウンロードします。(docker registryにはrate lmitがあるため本環境ではRedHatのquay.ioをレジストリとして利用します。)

```execute
docker pull quay.io/mnara/centos
```

imagesコマンドでローカルに存在するコンテナイメージを確認します。

```execute
docker images
```


