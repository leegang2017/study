

引用 [http://kafka.apache.org/quickstart](http://kafka.apache.org/quickstart)
 [https://www.cnblogs.com/likehua/p/3999538.html](https://www.cnblogs.com/likehua/p/3999538.html)



kafka-console-producer.sh send key value
```sh
$KAFKA_HOME/bin/kafka-console-producer.sh \
  --broker-list localhost:9092 \
  --topic my-topic \
  --property "parse.key=true" \
  --property "key.separator=:"
key1:value1
key2:value2
```