FROM centos:7

RUN yum install -y java-1.8.0-openjdk-headless unzip gettext nmap-ncat openssl\
 && yum clean all -y

ARG version

# Rocketmq version
ENV ROCKETMQ_VERSION ${version}

# Rocketmq home
ENV ROCKETMQ_HOME  /opt/rocketmq-${ROCKETMQ_VERSION}
#ENV ROCKETMQ_HOME /opt/rocketmq-all-${ROCKETMQ_VERSION}-bin-release

WORKDIR  ${ROCKETMQ_HOME}

RUN mkdir -p \
 /opt/logs \
 /opt/store

# get the version
RUN curl https://dist.apache.org/repos/dist/release/rocketmq/${ROCKETMQ_VERSION}/rocketmq-all-${ROCKETMQ_VERSION}-bin-release.zip -o rocketmq.zip \
 && unzip rocketmq.zip \
 && mv rocketmq-all*/* . \
 && rmdir rocketmq-all*  \
 && rm rocketmq.zip

# add scripts
COPY scripts/ ${ROCKETMQ_HOME}/bin/

VOLUME /opt/logs /opt/store
