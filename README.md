# 하둡 클러스터 기본 포트(Port)
하둡 클러스터의 기본포트에 대해서 알아보겠습니다.

타입	|서버	|포트|	사용법
--|--|--|--
hdfs	|hdfs	|8020	|hadoop fs -ls hdfs://$(hostname -f):8020/
hdfs	|webhdfs|	50070	|curl -s http://$(hostname -f):50070/webhdfs/v1/?op=GETFILESTATUS
hdfs	|webhdfs-proxy|	14000	|curl -s "http:///$(hostname -f):14000/webhdfs/v1?op=GETFILESTATUS&user.name=hadoop"
yarn	|resourcemanager	|8032	|
yarn	|resourcemanager web UI|	8088	|lynx http://$(hostname -f):8088
yarn	|timelineserver	|8188	|curl -s http://$(hostname -f):8188/ws/v1/timeline
yarn	|yarn-proxy-server|	20888	|
Mapreduce|	historyserver|	19888	|curl -s http://$(hostname -f):19888/ws/v1/history/info
hive	|metastore	|9083	|thrift://$(hostname -f):9083
hive	|hive-server2	|10000	|jdbc:hive2://localhost:10000
hive	|hive-server2 web UI	|10002|	lynx http://$(hostname -f):10002
spark	|spark-history-server	|18080|	curl http://$(hostname -f):18080/api/v1/applications
spark	|livy-server	|8998|	lynx http://localhost:8998
kms	|hadoop-kms	|9700|	curl http://$(hostname -f):9700/kms/v1/keys/names
