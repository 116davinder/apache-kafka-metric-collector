# Kafka Metric Collector
It will collect apache kafka metric using JMX.

It will also collect system metrics like cpu,memory and disk using shutil and psutil.

# Example Run
```
python3 kafka-jmx-metric-collector.py /tmp/ kafka-dev
```
## Example Input File
```
kafka.controller:type=KafkaController,name=OfflinePartitionsCount
kafka.controller:type=KafkaController,name=ActiveControllerCount
kafka.controller:type=ControllerStats,name=LeaderElectionRateAndTimeMs
kafka.controller:type=ControllerStats,name=UncleanLeaderElectionsPerSec
```
## Example OutPut File Size
```
$ ls -lh /tmp/*.log
-rw-rw-rw- 1 davinderpal davinderpal  10K Apr  2 12:23 /tmp/java.lang.log
-rw-rw-rw- 1 davinderpal davinderpal 5.8K Apr  2 12:23 /tmp/kafka.controller.log
-rw-rw-rw- 1 davinderpal davinderpal 149K Apr  2 12:23 /tmp/kafka.log.log
-rw-rw-rw- 1 davinderpal davinderpal  44K Apr  2 12:24 /tmp/kafka.network.log
-rw-rw-rw- 1 davinderpal davinderpal 4.7K Apr  2 12:24 /tmp/kafka.server.log
-rw-rw-rw- 1 davinderpal davinderpal 1.4K Apr  2 12:24 /tmp/kafka.utils.log
```

## Example Output
```
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=KafkaController,name=OfflinePartitionsCount/Value", "queryValue": "0"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=KafkaController,name=ActiveControllerCount/Value", "queryValue": "1"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=LeaderElectionRateAndTimeMs/LatencyUnit", "queryValue": "MILLISECONDS"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=LeaderElectionRateAndTimeMs/RateUnit", "queryValue": "SECONDS"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=LeaderElectionRateAndTimeMs/FiveMinuteRate", "queryValue": "1.4821969375e-313"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=LeaderElectionRateAndTimeMs/FifteenMinuteRate", "queryValue": "4.44659081257e-313"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=LeaderElectionRateAndTimeMs/OneMinuteRate", "queryValue": "2.964393875e-314"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=LeaderElectionRateAndTimeMs/MeanRate", "queryValue": "1.7414624729062179e-06"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=LeaderElectionRateAndTimeMs/EventType", "queryValue": "calls"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=LeaderElectionRateAndTimeMs/Max", "queryValue": "381.08192"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=LeaderElectionRateAndTimeMs/Count", "queryValue": "3"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=LeaderElectionRateAndTimeMs/StdDev", "queryValue": "174.11894949590612"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=LeaderElectionRateAndTimeMs/Min", "queryValue": "63.549557"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=LeaderElectionRateAndTimeMs/99thPercentile", "queryValue": "381.08192"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=LeaderElectionRateAndTimeMs/999thPercentile", "queryValue": "381.08192"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=LeaderElectionRateAndTimeMs/50thPercentile", "queryValue": "98.492782"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=LeaderElectionRateAndTimeMs/75thPercentile", "queryValue": "381.08192"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=LeaderElectionRateAndTimeMs/95thPercentile", "queryValue": "381.08192"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=LeaderElectionRateAndTimeMs/98thPercentile", "queryValue": "381.08192"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=LeaderElectionRateAndTimeMs/Mean", "queryValue": "181.04141966666666"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=UncleanLeaderElectionsPerSec/Count", "queryValue": "0"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=UncleanLeaderElectionsPerSec/RateUnit", "queryValue": "SECONDS"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=UncleanLeaderElectionsPerSec/FiveMinuteRate", "queryValue": "0.0"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=UncleanLeaderElectionsPerSec/FifteenMinuteRate", "queryValue": "0.0"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=UncleanLeaderElectionsPerSec/OneMinuteRate", "queryValue": "0.0"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=UncleanLeaderElectionsPerSec/MeanRate", "queryValue": "0.0"}
{"@timestamp": "2020-04-01 18:16:35.180486", "controllerName": "kafka.controller", "environment": "kafka-dev", "queryName": "type=ControllerStats,name=UncleanLeaderElectionsPerSec/EventType", "queryValue": "elections"}
....
```
