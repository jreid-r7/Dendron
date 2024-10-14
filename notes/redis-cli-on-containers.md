---
id: r6wujx3gglc3l3i49i8rgo2
title: Redis CLI on Containers
desc: ''
updated: 1723638383151
created: 1723638383151
isDir: false
id_imported: 0qp9y9sygzo5aqkrxqr1bu0
title_imported: Redis CLI on Containers
desc_imported: ''
updated_imported: 1723636850020
created_imported: 1723636850020
---
`kubectl config current-context`
Switch to prod context:
`kubectl config use-context arn:aws:eks:eu-central-1:124359542442:cluster/ipims-prod-0`
back to staging:
``kubectl config use-context arn:aws:eks:us-east-``1``:``529124731694``:cluster/ipims-staging-``1``

`kubectl run tmp-shell-$USER -l app=ipimsrbacpi --rm -i --tty --image redis -- /bin/bash`
or
`kubectl exec --stdin --tty tmp-shell-$USER -- /bin/bash` if the pod is running.

`redis-cli -h ipims-prod-0-rbaccorecache-rg.30jgq5.ng.0001.euc1.cache.amazonaws.com

`redis-cli -h ipims-staging-1-rbaccorecache-rg.d2uuh7.ng.0001.use1.cache.amazonaws.com`
`keys com/rapid7/heimdall/authorization/uap/uapType/2/organization*`

Delete a load of keys:
`redis-cli -h ipims-prod-0-rbaccorecache-rg.30jgq5.ng.0001.euc1.cache.amazonaws.com KEYS "com/rapid7/heimdall/authorization/uap/uapType/2/organization*" | xargs redis-cli -h ipims-prod-0-rbaccorecache-rg.30jgq5.ng.0001.euc1.cache.amazonaws.com DEL`
