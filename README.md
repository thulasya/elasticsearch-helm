# elasticsearch-helm
elasticsearch and curator using helm with custom

when namesapce is log-elasticsearch

helm repo add stable https://kubernetes-charts.storage.googleapis.com

helm install -f data.yaml es-data elastic/elasticsearch --namespace log-elasticsearch

helm install -f master.yaml es-master elastic/elasticsearch --namespace log-elasticsearch

helm install -f data.yaml es-data elastic/elasticsearch --namespace log-elasticsearch

helm install -f client.yaml es-client elastic/elasticsearch --namespace log-elasticsearch

helm install kibana elastic/kibana --set elasticsearchHosts=http://elasticsearch-client-headless.log-elasticsearch.svc.cluster.local:9200 --namespace log-elasticsearch

helm install -f curator.yaml elasticsearch-curator stable/elasticsearch-curator --namespace=log-elasticsearch
