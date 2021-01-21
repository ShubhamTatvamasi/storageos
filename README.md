# storageos

Install Prerequisites on Node:
```bash
sudo apt -y update
sudo apt -y install linux-modules-extra-$(uname -r)
```

Install storageos:
```bash
curl -sL https://storageos.run | bash
```

Dashboard: http://localhost:5705
```bash
kubectl port-forward -n kube-system svc/storageos 5705
```
> Dashboard ID and Password both: `storageos`

Get uid for cluster:
```bash
kubectl get storageclass -o yaml | grep uid
```

Make storageOS default class:
```bash
kubectl patch storageclass fast \
  --patch='{
    "metadata": {
      "annotations": {
        "storageclass.kubernetes.io/is-default-class": "true"
      }
    }
  }'
```

Verify:
```bash
kubectl get storageclass
```
