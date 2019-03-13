# docker-jenkins-gradle


docker run -d --restart=always --name jenkins -e TZ=Asia/Shanghai  -v /data/jenkins:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock --privileged=true -p 8100:8080 yangguoliang/docker-jenkins-gradle-maven:latest


docker run -d --restart=always --name jenkins-1 -e TZ=Asia/Shanghai -v /var/run/docker.sock:/var/run/docker.sock --privileged=true -p 8101:8080 duanzonglong/docker-jenkins-gradle:lst

编译镜像
docker build -t registry.cn-hangzhou.aliyuncs.com/yangguoliang/jenkins:latest ./


登录阿里云
docker login --username=19951761632 registry.cn-hangzhou.aliyuncs.com

push镜像
docker push registry.cn-hangzhou.aliyuncs.com/yangguoliang/jenkins:latest

启动
docker run -d --restart=always --name jenkins -e TZ=Asia/Shanghai  -v /data/jenkins:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock --privileged=true -p 8100:8080  registry.cn-hangzhou.aliyuncs.com/yangguoliang/jenkins:latest
