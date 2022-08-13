### On the Kube master server (` Master Only `)
```bash
# Configure cgroup driver used by kubelet on control-plane.(Only on master node)
	sudo docker info | grep -i cgroup

echo "Environment="KUBELET_CGROUP_ARGS=--cgroup-driver=cgroupfs"" >> /etc/systemd/system/kubelet.service.d/10-kubeadm.conf

systemctl restart kubelet

systemctl daemon-reload
