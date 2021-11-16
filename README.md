# Setting up ArgoCD with the Community Operator on OpenShift

```oc new-project argocd```

Install Community Operator in that project

Create ArgoCD instance with defaults ("example-argocd"):

```oc apply -f argocd-instance.yaml -n argocd```

```oc adm policy add-cluster-role-to-user cluster-admin -z example-argocd-argocd-application-controller -n argocd```

Check if custom resources are available:

```oc get crd | grep argo```

For "admin" password see secret/example-argocd-cluster

Optional:

```git clone https://github.com/guhilling/argocd-example-apps.git```

install guestbook-kustomize


# ArgoCD Example Apps

## Only kustomize-guestbook is supported!

This repository contains example applications for demoing ArgoCD functionality. Feel free
to register this repository to your ArgoCD instance, or fork this repo and push your own commits
to explore ArgoCD and GitOps!

| Application | Description |
|-------------|-------------|
| [helm-guestbook](helm-guestbook/) | The guestbook app as a Helm chart |
| [kustomize-guestbook](kustomize-guestbook/) | The guestbook app as a Kustomize 2 app |
| [pre-post-sync](pre-post-sync/) | Demonstrates Argo CD PreSync and PostSync hooks |
| [sync-waves](sync-waves/) | Demonstrates Argo CD sync waves with hooks |
| [sock-shop](sock-shop/) | A microservices demo app (https://microservices-demo.github.io) |
| [plugins](plugins/) | Apps which demonstrate config management plugins usage |
