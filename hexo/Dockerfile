FROM node
MAINTAINER znznzn707,<znznzn707@163.com>
LABEL description="The hexo with git"
LABEL version="1.0"
RUN npm --registry=https://registry.npm.taobao.org install hexo-cli -g && npm install && \
    mkdir /opt/Blog
ENV GIT_USER_NAME="test"
ENV GIT_USER_EMAIL="test@example.com"
ENV SSH_KEY="id_rsa"
COPY id_rsa /root/.ssh/
WORKDIR /opt/Blog
RUN chmod 600 /root/.ssh/$SSH_KEY && \
    ssh-agent ssh-add /root/.ssh/$SSH_KEY && \
    git config --global user.name $GIT_USER_NAME && \ 
    git config --global user.email $GIT_USER_EMAIL
RUN hexo init && \
    npm install hexo-deployer-git --save && \
    hexo clean && hexo g
VOLUME /opt/Blog 
VOLUME /root/.ssh
EXPOSE 4000
CMD hexo s
