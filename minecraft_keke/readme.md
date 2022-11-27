helm repo add itzg https://itzg.github.io/minecraft-server-charts/
helm upgrade --install -f minecraft_keke/values.yaml --namespace=minecraft-keke --create-namespace minecraft itzg/minecraft
helm uninstall --namespace=minecraft-keke  minecraft