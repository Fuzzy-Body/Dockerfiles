# 常用的dockerfile 合集

----

进入目录相应目录，运行

        docker build -t "fuzzy-body/python" .

----

### python容器使用

最好把Dockerfile拷贝到项目目录下，假设requirements.txt在根目录下，构建镜像

        docker build --no-cache --build-arg requirement=requirement.txt -t "fuzzy-body/python" .

使用镜像

        docker run -it --rm -v path-to-app:/opt/app -p 5000:5000 fuzzy-body/python

默认是执行 runserver.sh， 也可以使用自己的命令。--rm: 退出后自动删除容器

----

TODO: compose      
