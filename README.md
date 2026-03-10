# ☸️ Установка операторов в Kubernetes

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
