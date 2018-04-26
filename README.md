Add repository:
- helm repo add sample 'https://raw.githubusercontent.com/AlexxxTremer/exchange-listener-helm/master/'
- helm repo update

Check package avaliable:
- helm search exchangelistener

Install chart example:
- helm install sample/exchangelistener --name=exchangelistener --namespace=bpmonline

Update chart example:
- helm upgrade exchangelistener sample/exchangelistener

Avaliable values:

|parameter|description|default value|
|---|---|---|
|replicaCount| number of pods in statefull set| 2 |
|image.pullPolicy|pods image update policy|Always|
|service.type| service type| NodePort|
|service.nodePort| service external port|31313|
|ingress.enabled| use ingress|true|
|ingress.path|service ingress path|/exchangelistener|
|ingress.annotations.ingress.kubernetes.io/ssl-redirect|ssl trafic redirect flag|false|
|env| pod enviroment variables list||


|Enviroment variable path|description|default value|
|---|---|---|
|ExchangeListenerRedisHost| redis host path|redis-master.external-services:6379|
|ExchangeListenerRedisDatabase| redis database number| 0|
|MaxBpmonlineDownTime| max bpm'online unavaliable time in minutes, before subscription will be closed.|10|
|PodName|listener container name|value from metadata.name field|
