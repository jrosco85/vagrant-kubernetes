
I COULD LOG PODS FROM WORKERS!!!!! Vagrant create two interfaces
------------------------------------------------------------------------------

https://medium.com/@joatmon08/playing-with-kubeadm-in-vagrant-machines-part-2-bac431095706

vi /etc/systemd/system/kubelet.service.d/10-kubeadm.conf
Environment="KUBELET_EXTRA_ARGS=--node-ip=<worker IP address>"
sudo systemctl restart kubelet


METRIC-SERVER
-------------------------------------------------------------------------------
https://medium.com/@cagri.ersen/kubernetes-metrics-server-installation-d93380de008



GET TOKEN TO ACCESS CONSOLE
kubectl -n kubernetes-dashboard describe secret $(kubectl -n kubernetes-dashboard get secret | grep admin-user | awk '{print $1}')




REGISTRY
----------------------------------------------------------------------------------
- Expose the service
kubectl expose deployment docker-registry-deployment --type=NodePort --name=docker-registry-service -n docker-registry-local
