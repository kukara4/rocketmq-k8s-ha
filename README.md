# rocketmq-k8s-ha

bash bin/mqbroker -c conf/2m-2s-sync/broker-a.properties -n 172.17.0.2:9876  
docker run -dit -p 10911:10911 -p 10909:10909 --name rmqbroker rocket-broker  
bash bin/mqbroker -c conf/2m-2s-sync/broker-b-s.properties -n "172.17.0.2:9876;172.17.0.8:9876"  
./bin/mqadmin clusterList -n 172.17.0.2:9876  
docker build -t rocket-broker .
build -t apache/rocketmq-base:4.3.0 --build-arg version=4.3.0 ./rocketmq-base
