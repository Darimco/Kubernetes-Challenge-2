# Kubernetes-Challenge-2
## 1. Control plane

kubeconfig = /root/.kube/config, User = 'kubernetes-admin' Cluster: Server Port = '6443
#### kubectl get nodes 
#### systemctl status kubelet
#### cat .kube/config | grep control   (to rectify port# and restart the deamon)
#### vi .kube/config (change to the correct port #)
#### cat .kube/config | grep control
#### systemctl status kubelet
#### kubectl get nodes
#### cd /var/log/pods/
#### ls -ltr
#### cat ________apiserver-controlplane
#### ls -l /etc/kubernetes/pki/
#### cat /etc/kubernetes/manifests/kube-apiserver.yaml | grep crt
#### vi /etc/kubernetes/manifests/kube-apiserver.yaml   (change "ca-authority.crt" to "ca.crt")
#### systemctl status kubelet
#### systemctl restart kubelet
#### systemctl status kubelet
#### kubectl get nodes 
#### kubectl get pods -A
#### kubectl describe pod ______________________ -n kube-system
#### kubectl set image deployment/coredns -n kube-system  coredns=registry.k8s.io/coredns/coredns:v1.8.6
#### kubectl get pods -A


## 2. node01 is ready and can schedule pods?
uncordon the node
#### kubectl uncordon _____
#### kubectl get nodes

## 3. Copy all images from the directory '/media' on the controlplane node to '/web' directory on node01
#### ls /media/
#### scp /media/* node01:/web

## 4. Data -PV
Create new PersistentVolume = 'data-pv'

## 5. Data-PVC
Create new PersistentVolumeClaim = 'data-pvc'

## 6.  Gop-file-server
Create a pod for fileserver, name: 'gop-fileserver'

## 7. Gop-fs-service
New Service, name
