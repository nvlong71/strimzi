# strimzi
Setup kafka + dbz with strimzi



curl -s http://localhost:8083/connector-plugins/io.debezium.connector.mysql.MySqlConnector/config/validate   -X PUT   -H "Content-Type: application/json"   -d '{
    "database.hostname": "mysql",
    "connector.class": "io.debezium.connector.mysql.MySqlConnector",
    "database.port": "3306",
    "database.user": "root",
    "database.password": "debezium",
    "database.server.id": "184054",
    "topic.prefix": "mysql",
    "name": "connector",
    "database.server.name": "mysql:3306",
    "database.include.list": "inventory",
    "schema.history.internal.kafka.bootstrap.servers": "debezium-cluster-kafka-bootstrap:9092",
    "schema.history.internal.kafka.topics": "schema-changes.inventory"
  }' | jq . > log.json



  curl -S http://localhost:8083/connectors/debezium-connector-mysql/status