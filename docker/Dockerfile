FROM node:latest
RUN apt-get update
RUN apt-get install -y sudo git nano curl

WORKDIR /opt/
RUN git clone https://github.com/Stackout/nomp

WORKDIR /opt/nomp
RUN npm install
RUN npm update
RUN rm -rf pool_configs
RUN rm config_example.json

RUN ln -s /opt/config/config.json /opt/nomp/config.json
RUN ln -s /opt/config/pool_configs /opt/nomp/pool_configs

RUN apt-get install -y redis-server

CMD service redis-server restart; node init.js