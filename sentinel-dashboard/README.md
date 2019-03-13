alibaba sentinel dashboard docker 

TAGS
1.4.2, latest

VOLUME
容器内日志目录：/opt/logs

run
docker run --name sentinel -p 8080:8080 -v ./logs:/opt/logs registry.cn-hangzhou.aliyuncs.com/yangguoliang/sentinel-dashboard:1.4.2
或

docker run -e JAVA_OPTS='-Xmx1g' --name sentinel -p 8080:8080 registry.cn-hangzhou.aliyuncs.com/yangguoliang/sentinel-dashboard:1.4.2
或

docker run --rm --name sentinel -p 8080:8080 registry.cn-hangzhou.aliyuncs.com/yangguoliang/sentinel-dashboard:1.4.2
或

docker run --rm -e JAVA_OPTS='-Xmx1g' --name sentinel -p 8080:8080 registry.cn-hangzhou.aliyuncs.com/yangguoliang/sentinel-dashboard:1.4.2
官网
https://github.com/alibaba/Sentinel

新手指南

https://github.com/alibaba/Sentinel/wiki/新手指南

根据 Dockerfile 自己编译
编译镜像

docker build -t registry.cn-hangzhou.aliyuncs.com/yangguoliang/sentinel-dashboard:1.4.2 --build-arg version=1.4.2 ./

登录阿里云
sudo docker login --username=19951761632 registry.cn-hangzhou.aliyuncs.com

push镜像
sudo docker push registry.cn-hangzhou.aliyuncs.com/yangguoliang/sentinel-dashboard:1.4.2

启动容器
docker run --rm --name sentinel -p 8080:8080 registry.cn-hangzhou.aliyuncs.com/yangguoliang/sentinel-dashboard:1.4.2

或
docker run --rm -e JAVA_OPTS="-Dserver.port=8080 -Dcsp.sentinel.dashboard.server=localhost:8080 -Dproject.name=sentinel-dashboard -Djava.security.egd=file:/dev/./urandom" --name sentinel -p 8080:8080 registry.cn-hangzhou.aliyuncs.com/yangguoliang/sentinel-dashboard:1.4.2


docker run -d --restart=always -e JAVA_OPTS="-Dserver.port=8080 -Dcsp.sentinel.dashboard.server=localhost:8080 -Dproject.name=sentinel-dashboard -Djava.security.egd=file:/dev/./urandom" --name sentinel-dashboard -p 8849:8080 registry.cn-hangzhou.aliyuncs.com/yangguoliang/sentinel-dashboard:1.4.2
