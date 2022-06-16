# learn-docker

正常启动：
```shell
python3 simple-http-server/app.py
```

访问 server：
```shell
[ip]:8008     # 查看 server app pid
[ip]:8008/ps  # 查看服务器进程
[ip]:8008/ls  # 查看服务器根目录
```

制作 docker 镜像：
```shell
docker build -t stanley/simple-http-server:1.0 simple-http-server/
```

以 docker 模式启动：
```shell
# 除了进程与文件系统，docker 也隔离了网络协议栈
# 因此需要使用 -p 8008:8008 把 app 进程的端口号映射到宿主机
docker run --rm -t -p 8008:8008 stanley/simple-http-server:1.0
```