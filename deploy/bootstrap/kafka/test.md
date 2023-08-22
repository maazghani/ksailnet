```bash
./kafka-topics.sh --create --topic test-topic --bootstrap-server kafka-0.kafka-headless.default.svc.cluster.local:9092 
--replication-factor 1 --partitions 1

./kafka-console-producer.sh --topic test-topic --bootstrap-server kafka-0.kafka-headless.default.svc.cluster.local:9092

./kafka-console-consumer.sh --topic test-topic --from-beginning --bootstrap-server kafka-0.kafka-headless.default.svc.cluster.local:9092

./kafka-topics.sh --describe --topic test-topic --bootstrap-server kafka-0.kafka-headless.default.svc.cluster.local:9092

./kafka-topics.sh --alter --topic test-topic --bootstrap-server kafka-0.kafka-headless.default.svc.cluster.local:9092 --partitions 3

./kafka-topics.sh --describe --topic test-topic --bootstrap-server kafka-0.kafka-headless.default.svc.cluster.local:9092

./kafka-topics.sh --delete --topic test-topic --bootstrap-server kafka-0.kafka-headless.default.svc.cluster.local:9092
