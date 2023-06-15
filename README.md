
# Kafka

Instance for food delivery platform.

## Topics


|TOPIC                  |KEY        |
|-----------------------|-----------|
|merchants.menu-updates |merchantId |
|merchants.order-placed |merchantId |

### Create topics

```
kafka-topics --create --topic merchants.menu-updates --bootstrap-server localhost:9092

kafka-topics --create --topic merchants.order-placed --bootstrap-server localhost:9092

```

## Create Stack

```
kubectl create -f zoo1-deployment.yaml --context kind-food-delivery-cluster
kubectl create -f zoo1-service.yaml --context kind-food-delivery-cluster
kubectl create -f kafka1-deployment.yaml --context kind-food-delivery-cluster
kubectl create -f kafka1-service.yaml --context kind-food-delivery-cluster
```

# Kubernetes

To enter Kafka container

```
kubectl --context kind-<cluster name> exec kafka-broker-<pod-id>  -it -- /bin/sh

kubectl --context kind-food-delivery-cluster exec kafka-broker-<pod-id> -it -- /bin/sh
```


## Kafka cheats

### Create topic

```
kafka-topics.sh --create --topic <topic name> --bootstrap-server localhost:9092

kafka-topics.sh --create --topic merchants.order-placed --bootstrap-server localhost:9092
```


### Read topic

```
kafka-console-consumer.sh --topic <topic name> --from-beginning --bootstrap-server localhost:9092

kafka-console-consumer.sh --topic merchants.order-placed --from-beginning --bootstrap-server localhost:9092

```


### List topics

```
kafka-topics.sh --list --bootstrap-server localhost:9092
```