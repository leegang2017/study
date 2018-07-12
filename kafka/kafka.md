

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

ubuntu18.04 里面安装node-rdkafka，运行会报
```sh
Error: librdkafka.so.1: cannot open shared object file: No such file or directory
```
运行ldd build/Release/node-librdkafka.node，发现librdkafka.so.1没有
```sh
ldd build/Release/node-librdkafka.node
  linux-vdso.so.1 (0x00007ffc19131000)
  librdkafka++.so.1 => /data/work/github/node-rdkafka/build/deps/librdkafka++.so.1 (0x00007fae520e3000)
  libstdc++.so.6 => /usr/lib/x86_64-linux-gnu/libstdc++.so.6 (0x00007fae51d55000)
  libpthread.so.0 => /lib/x86_64-linux-gnu/libpthread.so.0 (0x00007fae51b36000)
  libc.so.6 => /lib/x86_64-linux-gnu/libc.so.6 (0x00007fae51745000)
  librdkafka.so.1 => not found
  libgcc_s.so.1 => /lib/x86_64-linux-gnu/libgcc_s.so.1 (0x00007fae5152d000)
  libm.so.6 => /lib/x86_64-linux-gnu/libm.so.6 (0x00007fae5118f000)
  /lib64/ld-linux-x86-64.so.2 (0x00007fae52542000
  ```
  临时解决方案，运行后librdkafka.so.1会链接到系统的库
  sudo apt-get install librdkafka1 librdkafka-dev