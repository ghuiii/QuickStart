# Docker Quick Start

1. ``docker image ls``  列出本机镜像
2. ``docker image rm <image-id>`` 删除镜像
3. ``docker run [--name container-name] -i -t ubuntu /bin/bash``  以ubuntu镜像创建一个容器 > 启动 > 运行bash ([]内可指定容器名字，否则为默认名字)
4. ``docker run [--name container-name] -d ubuntu /bin/bash`` **-d**指定了创建守护式容器
5. ``docker ps -a`` 或``docker container ls -a`` 查看当前机器上所有的docker容器（不加-a 则查看当前在运行的docker容器）
6. ``docker start <container-name>`` 重新启动已经停止的容器（也可以以容器id启动）
7. ``docker attach <container-name>  ``  重新附着到正在运行的docker容器上(回到bash交互环境)
8. ``docker top <container-name>`` 查看container当前运行的进程
9. ``docker exec -t -i <container-name> /bin/bash`` 在运行的某个容器中启动一个shell
10. ``docker stop <container-name>`` 停止一个容器
11. ``docker inspect <container-name>`` 返回容器的详细信息
12. ``docker rm <container-name>`` 删除docker容器

