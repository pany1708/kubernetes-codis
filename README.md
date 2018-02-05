根据codis官方优化来的,取消了官方的HA,使用redis-sentinel来保证HA,采用持久化存储,使用前先创建好storageclass
集群开启了密码保护,默认链接redis密码123


## 创建和删除集群

### Build one codis cluster (codis master server has one slave)

```
$ sh start.sh create
```

### Clean up the codis cluster

```
$ sh start.sh delete
```

### Scale codis cluster proxy

```
$ sh start.sh scale-proxy $(number)
```

### Scale codis cluster server

```
$ sh start.sh scale-server $(number)
```
