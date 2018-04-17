Add repository:
- helm repo add sample 'https://raw.githubusercontent.com/AlexxxTremer/exchange-listener-helm/master/'
- helm repo update

Check package avaliable:
- helm search exchangelistener

Install chart:
- helm install sample/exchangelistener --name=exchangelistener --namespace=bpmonline

Update chart:
- helm upgrade exchangelistener sample/exchangelistener --set replicaCount=2
