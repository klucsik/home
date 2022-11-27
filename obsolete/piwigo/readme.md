helm repo add cronce https://charts.cronce.io/

helm upgrade --install --namespace=piwigo --create-namespace -f piwigo/values.yaml piwigo cronce/piwigo
csinálj secretet a tlsnek