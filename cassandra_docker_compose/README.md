Run the docker-compose for cassandra server

```sh
docker-compose up -d
```

Check the running container 

```sh
docker ps
```

To verify that everything is ok and the cluster is up and running, you can check the container logs or use a tool like nodetool 
to connect to one of the containers and then inspect the cluster status:

```sh
docker exec -it cassandra1 nodetool status
```

