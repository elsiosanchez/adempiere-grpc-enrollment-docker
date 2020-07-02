ADempiere Enrollment gRPC Docker Server
=====================
Use this server for enable all enrollment service data layer of ADempiere as a service, this docker project is related to https://github.com/erpcya/adempiere-gRPC-Server

[Docker](https://www.docker.io/) file for trusted builds of [ADempiere gRPC Deploy](http://erpya.com/) on https://hub.docker.com/r/erpya/adempiere-grpc-enrollment.

You will need use a file with a structure like it: [enrollment_connection.yaml](enrollment_connection.yaml)
```yaml

server:
    port: 50047
database:
    host: localhost
    port: 5432
    name: "database"
    user: adempiere
    password: adempiere
    type: PostgreSQL
```

Run the latest container with:
```shell
    docker pull erpya/adempiere-grpc-enrollment
```

```shell
docker run --name adempiere-grpc-enrollment -it \
	-p 50047:50047 \
	-v $(pwd)/enrollment_connection.yaml:/opt/Apps/ADempiere-gRPC-Server/bin/enrollment_connection.yaml \
	erpya/adempiere-grpc-enrollment
```
