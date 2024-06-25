# An implementation of the App of Apps pattern using ArgoCD (NOT FINISHED)

This arcticle describes a practical implementation of the app of apps pattern using argocd with a real-world example using helm templating.
This pattern in argocd allows to create a single application (let's call it *app-of-apps* for convenience) that contains that contain all the other applications that we want to deploy in the cluster.
This is specially useful when we want to bootstrap a cluster and want argocd to take care of deploying all the applications in the cluster.
In this scenario we only deploy the *app-of-apps* application, an as this application contains all the other applications as child apps, argocd will take care of deploying yhem.

This pattern is describes in argocd documentation: https://argo-cd.readthedocs.io/en/stable/operator-manual/cluster-bootstrapping/

Being practical, there are several cluster apps that we need when creating a cluster, like monitoring, logging, ingress,  controllers, etc.
Being specific now, *aws-load-balancer-controller*, *kube-prometheus-stack*,
