
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
kubectl --context kind-<cluster name> exec kafka1-<pod-id>  -it -- /bin/sh

kubectl --context kind-food-delivery-cluster exec kafka1-<pod-id>  -it -- /bin/sh
```


## Kafka cheats

### Create topic

```
kafka-topics --create --topic <topic name> --bootstrap-server localhost:9092
```


