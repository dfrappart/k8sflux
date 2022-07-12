# K8S Flux Lab

As the name implies, this is a repod for testing GitOps things through [flux](https://fluxcd.io/docs/)

```bash

flux create source git podinfo --url=https://github.com/stefanprodan/podinfo --branch=master --interval=30s --export > ./.clusters/testcluster/podinfo/podinfo-source.yaml

```

```bash

flux create kustomization podinfo --target-namespace=default --source=podinfo --path="./kustomize" --prune=true --interval=5m --export > ./cluster/testclusters/podinfo/podinfo-kustomization.yaml

```
