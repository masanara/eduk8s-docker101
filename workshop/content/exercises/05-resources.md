コンテナ起動時のオプションでCPUやメモリー等のリソースの制限が可能です。

- -m , --memory : メモリの上限（書式： <数値> [<単位>] 、単位は b、k、m、g のいずれか）
- --memory-swap : 合計メモリの上限（メモリ＋スワップ、書式： <数値> [<単位>] 、単位は b、k、m、g のいずれか）
- --memory-reservation : メモリのソフト・リミット（書式： <数値> [<単位>] 、単位は b、k、m、g のいずれか）
- --kernel-memory : カーネル・メモリの上限（書式： <数値> [<単位>] 、単位は b、k、m、g のいずれか）
- -c, --cpu-shares : CPU 共有（CPU shares）を相対値で指定
- --cpu-period : CPU CFS (Completely Fair Scheduler) ピリオドの上限（訳者注：cgroup による CPU リソースへのアクセスを再割り当てする間隔）
- --cpuset-cpus : 実行する CPU の割り当て（0-3, 0,1）
- --cpuset-mems : 実行するメモリ・ノード（MEM）の割り当て（0-3, 0,1）。NUMA システムのみで動作
- --cpu-quota : CPU CFS (Completely Fair Scheduler) のクォータを設定
- --blkio-weight=0 : ブロック I/O ウエイト（相対値）を 10 ～ 1000 までの値でウエイトを設定
- --oom-kill-disable=false : コンテナを OOM killer による停止を無効化するかどうか指定
- --memory-swappiness="" : コンテナがメモリのスワップ度合いを調整。整数値の 0 ～ 100 で指定

利用可能なパラメータの詳細は以下のマニュアルを参照してください。

- [Runtime options with Memory, CPUs, and GPUs](https://docs.docker.com/config/containers/resource_constraints/)
