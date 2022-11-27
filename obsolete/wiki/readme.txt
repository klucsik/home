helm repo add requarks https://charts.js.wiki

helm upgrade -f wiki/yrelia/yrelia-values.yaml --install yrelia-wiki --namespace=yrelia-wiki --create-namespace requarks/wiki
kubectl apply -f wiki/yrelia/psql-deployment.yaml


helm upgrade -f wiki/mare-stellarum/mare-stellarum-values.yaml --install mare-stellarum-wiki --namespace=mare-stellarum-wiki --create-namespace requarks/wiki
kubectl apply -f wiki/mare-stellarum/psql-deployment.yaml



helm uninstall yrelia-wiki --namespace=yrelia-wiki