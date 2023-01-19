# reids笔记

docker启动redis镜像 命令

```sh
docker run -itd ^
--name my-redis ^
-p 6379:6379  ^
-v=D:/DevOps/docker/volume/database/redis/redis.conf:/redisConfig/redis.conf ^
-v=D:/DevOps/docker/volume/database/redis/data:/data ^
redis:7.0 redis-server /redisConfig/redis.conf
```

