コンテナイメージはdocker buildコマンドで作成することが可能です。docker buildはDockerfileと呼ばれるコンテナの設計図を読み込んでコンテナイメージを作成します。

用意されているDockerfileを確認します。

```execute
cd $HOME/contents; cat Dockerfile
```

index.htmlファイルが用意されています。index.htmlファイルにdateコマンドで日付を追加します。

```execute
date >> index.html
```

```execute
cat index.html
```

このDockerファイルはUbuntuのベースイメージにnginxを追加し、ログを標準出力に変更して、index.htmlファイルをコンテナイメージ内にコピーします。

docker buildを実行してコンテナをビルドします。```-t```で作成するコンテナイメージを指定します。

```execute
docker build -t mynginx .
```

作成が完了したら、ローカルに存在するsコンテナイメージを確認します。

```execute
docker images
```

作成したイメージでコンテナを起動してみます。

```execute
docker run -itd --name mynginx -p 8081:80 mynginx
```

起動を確認します。

```execute
docker ps
```

コンテナにアクセスできることを確認します。

```execute
curl localhost:8081
```

コンテナはDockerfileに指定された内容を順番に実行していき、各行に対して1つのレイヤーを作成します。。

Dockerfileの行数を減らすことでイメージ数を削減可能です。パッケージマネージャを利用してソフトウェアをインストールする場合、同じ命令内パッケージマネージャが生成する一時ファイルやキャッシュを削除することで、コンテナイメージを小さくすることも可能です。。

```execute
docker history mynginx
```

Dockerfileを編集してイメージを更新する場合、更新行までの内容はキャッシュされるため高速にbuild可能です。 例えば、DockerfileでEXPOSE行だけ変更した場合、apt-getコマンドを実行したレイヤーは再利用される、EXPOSEのレイヤー以降が新しく作成されます。

起動したmynginxコンテナを停止して削除します。

```execute
docker rm -f mynginx
```
