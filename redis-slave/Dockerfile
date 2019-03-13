FROM redis:3-alpine
MAINTAINER ygl

#COPY Shanghai /etc/localtime
COPY redis.conf /redis/redis.conf
COPY sentinel.conf /redis/sentinel.conf
COPY start.sh /redis/start.sh
RUN chmod +x /redis/start.sh
RUN chown redis:redis /redis/*
ENTRYPOINT ["sh","/redis/start.sh"]
# 传参覆盖变量
CMD ["master"]
