# Minecraft Helm Chart

A quick way to setup minecraft on a k8s to play with friends

## Installation

```bash
# cloning chart repository
git clone https://github.com/okunix/minecraft-charts

# installing minecraft chart on existing cluster
helm install minecraft ./minecraft --namespace minecraft --create-namespace

# checking chart status
helm status -n minecraft minecraft

# upgrading example
helm upgrade minecraft ./minecraft --namespace minecraft --set minecraft.VERSION="1.21.10"

# to uninstall chart use
helm uninstall minecraft -n minecraft

# to get service IP use following command and search for an external ip
k get -n minecraft svc
```
