FROM kukara4/k8s-rocket-mq-base

EXPOSE 10909 10911

RUN mv ${ROCKETMQ_HOME}/bin/runbroker-customize.sh ${ROCKETMQ_HOME}/bin/runbroker.sh \
 && chmod +x ${ROCKETMQ_HOME}/bin/runbroker.sh \
 && chmod +x ${ROCKETMQ_HOME}/bin/mqbroker

#CMD cd ${ROCKETMQ_HOME}/bin \
# && export JAVA_OPT=" -Duser.home=/opt" \
# && sh mqbroker

#ENTRYPOINT ["/bin/bash"]
