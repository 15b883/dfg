


通过Mac编译 Linux执行文件

```shell
CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o linuxgo main.go
```

docker build 

```shell
docker build . -t linuxgo:v1 
```

run docker
```shell
docker run -d --name=linuxgo  hellogo:v1
```

```shell
➜  hellogo docker run -d --name=linuxgo  linuxgo:v1
30770c0842aca9e19faa9ca5715b1181ee6c22f7f9e64fb59f17d113d1e2424d
➜  hellogo docker ps -a                            
CONTAINER ID   IMAGE        COMMAND          CREATED          STATUS                      PORTS     NAMES
30770c0842ac   linuxgo:v1   "/app/linuxgo"   16 seconds ago   Exited (0) 14 seconds ago             linuxgo
➜  hellogo docker logs 30770c0842ac
hello go

```