# 构建docker镜像

### jenkins
1. 包含gradle 4.10,npm 10.15.3,maven 3.6.0
2. 启动：
docker run -d --restart=always --name jenkins -e TZ=Asia/Shanghai  -v /data/jenkins:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock --privileged=true -p 8100:8080  registry.cn-hangzhou.aliyuncs.com/yangguoliang/jenkins:latest

### sentinel-dashboard
1. alibaba sentinel-dashboard
2. 启动 
docker run -d --restart=always -e JAVA_OPTS="-Dserver.port=8080 -Dcsp.sentinel.dashboard.server=localhost:8080 -Dproject.name=sentinel-dashboard -Djava.security.egd=file:/dev/./urandom" --name sentinel-dashboard -p 8849:8080 registry.cn-hangzhou.aliyuncs.com/yangguoliang/sentinel-dashboard:1.4.2


### fastdfs


### redis主从
