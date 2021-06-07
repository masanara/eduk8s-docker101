ホストOSのディストリビューションを確認します。本環境ではFedoraが利用されています。

```execute
cat /etc/redhat-release
```

コンテナを起動してコンテナ内のbashで状態を確認してみます。

```execute
docker run -it quay.io/mnara/centos bash
```

コンテナ内のbashが起動し、CentOSであることが確認できます。

```execute
cat /etc/redhat-release
```

コンテナ内のプロセスを確認すると、bashだけが起動しています。また、bashのプロセスIDが1となっていることに注意してください。

```execute
ps ax
```

コンテナ内からCPU/Memoryを見ると、dockerホストのリソースがそのまま見えています。

```execute
cat /proc/cpuinfo
```

```execute
cat /proc/meminfo
```

