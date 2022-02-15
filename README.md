# kubernetes-microk8s

```bash
MICROK8S
sudo snap install microk8s --classic
FIREWALL
sudo ufw allow in on cni0 && sudo ufw allow out on cni0
sudo ufw default allow routed
DASHBOARD
microk8s enable dns dashboard storage
LIST
microk8s kubectl get all --all-namespaces


The actual kubeconfig file is at /var/snap/microk8s/current/credentials/client.config

To change the kubeconfig file used by microk8s.kubectl you can edit /var/snap/microk8s/current/args/kubectl-env



cd $HOME
mkdir .kube
cd .kube
microk8s config > config
```
