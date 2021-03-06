### ssh 实现端口转发

实例背景：公司有堡垒机，任何操作均需要在堡垒机上进行，有些开发人员需要访问 ELasticSearch 的 head 面板查看集群状态，但是我们并不想将 ElasticSearch 的 9200 端口映射出去，依然想通过堡垒机进行访问，所以才会将通往堡垒机（192.168.1.15）的请求转发到服务器 ElasticSearch（192.168.1.19）的 9200 上。

```bash
# 将发往本机（192.168.1.15）的 9200 端口访问转发到 192.168.1.19 的 9200 端口,前提是先进行秘钥传输

$ ssh -p 22 -C -f -N -g -L 9200:192.168.1.19:9200 user1@192.168.1.19
```
执行完命令后，访问 15:9200 端口实际是访问 19:9200 端口

> 命令选项：
>
> -C 请求压缩所有数据
>
> -f 后台执行 ssh 指令
>
> -N 不执行行程指令
>
> -g 允许行程主机连接主机的转发端口
>
> -L 端口转发
