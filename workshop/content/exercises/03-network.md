ifconfig/netstatを利用するためにdnfでnet-toolsをインストールします。

```execute
dnf install -y net-tools
```

コンテナのIPアドレスを確認します。

```execute
ifconfig
```

デフォルトルートはbridge0のアドレスが設定されています。

```execute
netstat -rn
```

デフォルトゲートウェイとなっているdocker0ブリッジにpingを打つと応答があります。

```execute
ping -c 2 172.17.0.1
```

コンテナ内から外部への通信はホストのIPアドレスを使ってNATされるため、コンテナ内から外部へ通信することは可能です。

```execute
curl -s -o /dev/null -D - https://www.google.com
```

