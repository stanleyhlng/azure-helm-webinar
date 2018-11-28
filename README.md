# azure-helm-webinar

**rainbow-kitten-surprise** is a very important application
that provides a unique sensory experience.

It is comprised of a simple frontend,
the [cat-service](https://github.com/codefresh-io/azure-demo-cat-service),
and the [color-service](https://github.com/codefresh-io/azure-demo-color-service).

To install (on Azure):

```
# Use your own AKS Cluster DNS Zone
export CLUSTER_DNS_ZONE="52fc7454c071a75fc1d3.eastus.aksapp.io"
export RELEASE_NAME="azdemo"

helm upgrade --install $RELEASE_NAME \
    --set clusterDnsZone=$CLUSTER_DNS_ZONE \
    rainbow-kitten-surprise/
    
echo "APP URL: http://$RELEASE_NAME.$CLUSTER_DNS_ZONE"
```

To uninstall:

```
helm uninstall $RELEASE_NAME --purge
```

## Pipeline Diagram

All pipeline definitions can be found in the [.codefresh/](.codefresh/) folder.

<img width="500px" src="Azure_Codefresh.png"/>
