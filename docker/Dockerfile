FROM node:9.4.0

RUN set -ex ; \
    apt update ; \
    apt install git python make g++ ; \
    mkdir -p /opt/nomp

COPY package.json /opt/nomp/

WORKDIR /opt/nomp

RUN npm update

COPY ../ /opt/nomp/

RUN rm -rf /opt/nomp/pool_configs
RUN ln -s /opt/config/config.json /opt/nomp/config.json
RUN ln -s /opt/config/pool_configs /opt/nomp/

VOLUME ["/opt/config"]

EXPOSE 80
EXPOSE 3333

CMD node init.js