helm upgrade --install -f minecraft/values.yaml --namespace=minecraft --create-namespace minecraft itzg/minecraft
helm uninstall --namespace=minecraft  minecraft