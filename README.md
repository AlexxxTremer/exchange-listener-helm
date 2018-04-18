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
- replicaCount: number of pods in statefull set. Default value: 2
- image.pullPolicy: pods image update policy. Default value: Always
- service.type: service type. Default value: NodePort
- service.nodePort: Default value: 31313
- ingress.enabled: use ingress template. Default value: true
- ingress.path: service ingress path. Default value: /exchangelistener
- ingress.annotations.ingress.kubernetes.io/ssl-redirect: ssl trafic redirect flag. Default value:"false"
- env: pod enviroment variables list. All pods use next enviroment variables:
  ExchangeListenerRedisHost: redis host path. Default value: redis.external-services:6379
  ExchangeListenerRedisDatabase: redis database number. Default value: 0
  MaxBpmonlineDownTime: max bpm'online unavaliable time in minutes, before subscription will be closed.
