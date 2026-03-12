# k8s-operators

## Установка операторов в kubernetes

```bash
# Strimzi (Kafka)
helm upgrade --install strimzi-operator \
    oci://quay.io/strimzi-helm/strimzi-kafka-operator \
    --set watchAnyNamespace=true \
    --namespace strimzi-system \
    --create-namespace
```

```bash
# CloudNativePG (Postgres)
helm repo add cnpg https://cloudnative-pg.github.io/charts
helm upgrade --install cnpg-operator \
    cnpg/cloudnative-pg \
    --namespace cnpg-system \
    --create-namespace
```

```bash
# Percona (MongoDB)
helm repo add percona https://percona.github.io/percona-helm-charts
helm upgrade --install percona-operator-crds \
    percona/psmdb-operator-crds \
    --namespace percona-system \
    --create-namespace
helm upgrade --install percona-operator \
    percona/psmdb-operator \
    --set watchAllNamespaces=true \
    --namespace percona-system \
    --create-namespace
```

```bash
# Redis OT-Container
helm repo add otredis https://ot-container-kit.github.io/helm-charts
helm upgrade --install redis-operator \
    otredis/redis-operator \
    --namespace redis-system \
    --create-namespace
```
