コンテナをバックグラウンドで起動してみます。 (-dオプション) バックグラウンドで起動しているため、docker run実行後もホストのシェルのままになります。```--name```オプションにより、コンテナに任意の名前をつけることが可能です。

```execute
docker run -tid --name mycentos quay.io/mnara/centos bash
```

起動したコンテナを確認します。mycentosコンテナのSTATUSがUPとなっていることを確認します。

```execute
docker ps -a
```

```attach```オプションで起動中にコンテナに接続することが可能です。プロンプトがコンテナに切り替わることを確認します。

```execute
docker attach mycentos
```

コンテナを起動したまま接続を切断するには、```C-p, C-q```と入力します。exitやログアウトを行うと、このコンテナはbashが終了するためコンテナごと停止してしまいます。

*** ```Ctrl+p, Ctrl+q```と入力して、コンテナのシェルから切断します。*** (切断しないと次ページ移行のハンズオンが正しく動作しません)

