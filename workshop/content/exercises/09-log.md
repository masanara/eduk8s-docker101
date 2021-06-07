docker execコマンドで指定したコンテナに対してコマンドを実行することが可能です。コンテナ内のnginxの設定ファイルを確認してみましょう。

```execute
docker exec nginx1 cat /etc/nginx/nginx.conf | grep log
```

コンテナ内のnginxはログファイルの出力先が標準出力/標準エラー出力にリダイレクトされています。

```execute
docker exec nginx1 ls -l /var/log/nginx/error.log
```

```execute
docker exec nginx1 ls -l /var/log/nginx/access.log
```

コンテナの標準出力/標準エラー出力はdocker logsコマンドで確認することができ、-fオプションによりリアルタイムに出力することが可能です。

```execute
docker logs -f nginx1
```

[コンテナが起動するポート]({{ ingress_protocol }}://{{ session_namespace }}-access1.{{ ingress_domain }})にアクセスしてページをリロードすると、アクセスログを確認することができます。

アクセスログを確認したら、ログ出力を停止します。

```execute
<ctrl+c>
```
