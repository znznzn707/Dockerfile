FROM redis:6.0.5
MAINTAINER znznzn707 <znznzn707@hotmail.com>
LABEL description="redis with redis.conf"
ENV REDIS_CONF=/usr/local/etc/redis/redis.conf
COPY redis.conf /usr/local/etc/redis/redis.conf
CMD [ "redis-server", "/usr/local/etc/redis/redis.conf"  ]
