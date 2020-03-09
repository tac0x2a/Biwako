# Biwako

[![Biwako](./doc/img/biwako.svg)](https://github.com/tac0x2a/biwako)

Biwako is an all in one micro Data Lake for IoT data.


# Services

## [RabbitMQ](https://www.rabbitmq.com/)
Message broker service. The MQTT port listen json format messages. Its general entry point of data stream to Biwako.

### Ports
+ 15672: Web management console. Default account is `guest`:`guest`.
+ 1883: MQTT port.

## [Grebe](https://github.com/tac0x2a/grebe)
Grebe is forwarder JSON message from RabbitMQ to Clickhouse.

## [ClickHouse](https://clickhouse.tech/)
ClickHouse is a free analytics DBMS for big data. Central data storage of Biwako.
Default database is `default`, and user name and password is `default`.

### Ports
+ 8123: HTTP client port.

## [Portainer](https://www.portainer.io/)
Portainer is a lightweight management UI. After login, please select `Local` and press `Connect` button.

### Ports
+ 9000: Web interface.

## [Metabase](https://www.metabase.com/)
Metabase visualize data on ClickHouse. It works with [metabase-clickhouse-driver](https://github.com/enqueue/metabase-clickhouse-driver).

In first access, you need to register ClickHouse table as data source.
+ Database type `ClickHouse`,
+ Database Name: any
+ Host: `clickhouse`
+ Port: `8123`
+ Database user name: `default`
+ Database password: empty

### Ports
+ 3000: Web interface.

## [Tabix](https://tabix.io/)
Open source simple business intelligence application and sql editor tool for Clickhouse.

+ Name: any
+ `http://host:port` : `http://<host-of-biwako-running>:8123`
+ Login: `default`
+ Password: empty
+ (Experimental) HTTP Base auth: True

### Ports
+ 8080: Web interface.
