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

Dashboard ID and Password both:
storageos

Get uid for cluster:
```bash
kubectl get StorageClass -o yaml | grep uid
```
