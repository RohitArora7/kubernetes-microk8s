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

```bash
HOST
> creating a microbot deployment with two pods via the kubectl cli:
microk8s kubectl create deployment microbot --image=dontrebootme/microbot:v1
microk8s kubectl scale deployment microbot --replicas=2
> expose our deployment we need to create a service:
microk8s kubectl expose deployment microbot --type=NodePort --port=80 --name=microbot-service
> list 
microk8s kubectl get all --all-namespaces

default       pod/microbot-5f5499d479-vznng                    1/1     Running   0          22s
default       pod/microbot-5f5499d479-6kq5r                    1/1     Running   0          22s

default       service/microbot-service            NodePort    10.152.183.69   <none>        80:32648/TCP             16s

http://localhost:32648
```

```bash
INTEGRATED COMMANDS
microk8s status: Provides an overview of the MicroK8s state (running / not running) as well as the set of enabled addons
microk8s enable: Enables an addon
microk8s disable: Disables an addon
microk8s kubectl: Interact with kubernetes
microk8s config: Shows the kubernetes config file
microk8s istioctl: Interact with the istio services; needs the istio addon to be enabled
microk8s inspect: Performs a quick inspection of the MicroK8s intallation
microk8s reset: Resets the infrastructure to a clean state
microk8s stop: Stops all kubernetes services
microk8s start: Starts MicroK8s after it is being stopped
```
