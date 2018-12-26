# 练习设计

按以下步骤完成练习

## 下载、解压并启动kafka

参考：http://kafka.apache.org/quickstart

1. 下载和解压

- [X] 下载kafka_2.11-2.1.0 [下载页面](http://kafka.apache.org/downloads)
- [ ] 解压至本地目录，如C:\kafka，下面以$KAFKA_HOME表示。

2. 启动kafka

- [ ] 新建命令行窗口(1)，cd $KAFKA_HOME，执行`bin/zookeeper-server-start.sh config/zookeeper.properties`，启动zookeeper
- [ ] 新建命令行窗口(2)，cd $KAFKA_HOME，执行`bin/kafka-server-start.sh config/server.properties`, 启动kafka

3. 验证kafka启动成功

- [ ] 新建命令行窗口(3)，cd $KAFKA_HOME，执行`bin/kafka-console-producer.sh --broker-list localhost:9092 --topic connect-test`，启动试验producer。
- [ ] 新建命令行窗口(4)，cd $KAFKA_HOME，执行`bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic connect-test --from-beginning`，启动试验consumer。
- [ ] 切换至命令行窗口(3)，输入“hello kafka"，回车。
- [ ] 切换至命令行窗口(4)，应该能看到"hello kafka"已经输出。

4. 关闭服务

- [ ] 切换至窗口3，4，按`Ctrl+C`退出producer和consumer进程。
- [ ] 待3，4退出完成，切换至窗口2，按`Ctrl+C`退出kafka。
- [ ] 待2退出完成，切换至窗口1，按`Ctrl+C`退出kafka。

## 使用java编写kafka-producer

参考：https://www.jianshu.com/p/4760279b4ead

- [ ] 把producer项目导入IDEA。
- [ ] 实现功能：从控制台接收输入，在输入信息前加上"receive:"，并输出到控制台。
- [ ] 实现功能：从控制台接收输入，把输入发送到kafka的connect-test topic。
- [ ] 启动zookeeper，kafka和kafka-console-consumer，在consumer中确认producer发出的消息和预期一致。

## 使用java编写kafka-consumer

参考：https://www.jianshu.com/p/4760279b4ead

- [ ] 把consumer项目导入IDEA。
- [ ] 实现功能：监听kafka的connect-test topic，并且把消息输出到控制台。
- [ ] 启动zookeeper，kafka和kafka-console-producer，通过producer发送消息，确认consumer能正确消费。

## 使用spring-boot进行重构

TBD