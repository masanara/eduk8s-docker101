コンテナイメージはRegistry上にアップロードして共有することが可能です。Registryへアップロードする際はコンテナイメージ名(タグ)にレジストリ名を含めます。

本環境では内部レジストリとして {{ registry_host }} を利用します。

レジストリにログインします。本環境ではすでにログイン済みであるため認証情報は求められませんが、通常レジストリのユーザー名・パスワードを求められます。

```execute
docker login {{ registry_host }}
```

作成したコンテナイメージにレジストリ名を含む新しいタグを付与します。

```execute
docker tag mynginx:latest {{ registry_host }}/mynginx:latest
```

タグが付与されたことを確認します。mynginxと新しいタグのIMAGE IDが同じ値であることに注目してください。

```execute
docker images
```

Registry ({{ registry_host }}) にイメージをプッシュします。

```execute
docker push {{ registry_host }}/mynginx:latest
```

ローカルコンテナイメージを削除します。

```execute
docker rmi mynginx:latest {{ registry_host}}/mynginx:latest
```

ローカルにコンテナイメージが無いことを確認します。

```execute
docker images
```

Registry上のイメージを指定してコンテナを起動します。

```execute
docker run -itd -p 8082:80 {{ registry_host }}/mynginx:latest
```

起動したコンテナにアクセスして、起動を確認します。

{{ ingress_protocol }}://{{ session_namespace }}-access3.{{ ingress_domain }}

