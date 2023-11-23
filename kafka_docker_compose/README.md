Run the docker-compose for Kafka server

```sh
docker-compose up -d
```

Check the running container 

```sh
docker ps
```

After a few minutes, if the state of any component isn’t Up, run the 

```sh
docker-compose restart <image-name>
```

---

For Kafka dev portal 

```sh
http://localhost:9021/
```

---

Running Container list after `docker-compose ps`


| Name             | Command                              | State | Ports                                              |
|------------------|--------------------------------------|-------|----------------------------------------------------|
| broker           | /etc/confluent/docker/run            | Up    | 0.0.0.0:9092->9092/tcp,:::9092->9092/tcp,           |
|                  |                                      |       | 0.0.0.0:9101->9101/tcp,:::9101->9101/tcp           |
| connect          | /etc/confluent/docker/run            | Up    | 0.0.0.0:8083->8083/tcp,:::8083->8083/tcp, 9092/tcp  |
| control-center   | /etc/confluent/docker/run            | Up    | 0.0.0.0:9021->9021/tcp,:::9021->9021/tcp           |
| ksql-datagen     | bash -c echo Waiting for K ...       | Up    |                                                    |
| ksqldb-cli       | /bin/sh                              | Up    |                                                    |
| ksqldb-server    | /etc/confluent/docker/run            | Up    | 0.0.0.0:8088->8088/tcp,:::8088->8088/tcp           |
| rest-proxy       | /etc/confluent/docker/run            | Up    | 0.0.0.0:8082->8082/tcp,:::8082->8082/tcp           |
| schema-registry  | /etc/confluent/docker/run            | Up    | 0.0.0.0:8081->8081/tcp,:::8081->8081/tcp           |

