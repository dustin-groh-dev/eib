Both nodes added to cluster.
```
2603-900a-2100-79da-0000-0000-0000-1034:~ # kubectl get nodes -o wide
NAME                                                        STATUS   ROLES                              AGE   VERSION        INTERNAL-IP   EXTERNAL-IP   OS-IMAGE               KERNEL-VERSION   CONTAINER-RUNTIME
2603-900a-2100-79da-0000-0000-0000-102e.inf6.spectrum.com   Ready    control-plane,etcd,master,worker   19h   v1.31.8+k3s1   10.27.27.79   <none>        SUSE Linux Micro 6.0   6.4.0-9-rt       containerd://2.0.4-k3s2
2603-900a-2100-79da-0000-0000-0000-1034.inf6.spectrum.com   Ready    control-plane,etcd,master,worker   12h   v1.31.8+k3s1   10.27.27.42   <none>        SUSE Linux Micro 6.0   6.4.0-9-rt       containerd://2.0.4-k3s2
```
k3s-selinux rpm installed.
```
2603-900a-2100-79da-0000-0000-0000-102e:~ # rpm -qa | grep selinux
libselinux1-3.5-3.1.x86_64
selinux-tools-3.5-3.1.x86_64
python3-selinux-3.5-3.1.x86_64
selinux-policy-20230523+git25.ad22dd7f-1.1.noarch
selinux-policy-targeted-20230523+git25.ad22dd7f-1.1.noarch
container-selinux-2.211.0-2.100.noarch
cockpit-selinux-309-6.1.noarch
patterns-base-selinux-6.0-1.1.x86_64
k3s-selinux-1.6-1.slemicro.noarch
```
selinux enforcing.
```
2603-900a-2100-79da-0000-0000-0000-102e:~ # sestatus
SELinux status:                 enabled
SELinuxfs mount:                /sys/fs/selinux
SELinux root directory:         /etc/selinux
Loaded policy name:             targeted
Current mode:                   enforcing
Mode from config file:          enforcing
Policy MLS status:              enabled
Policy deny_unknown status:     allowed
Memory protection checking:     actual (secure)
Max kernel policy version:      33
```
cattle-cluster agent working as expected.
```
2603-900a-2100-79da-0000-0000-0000-1034:~ # kubectl get pods -n cattle-system -o wide | grep agent
cattle-cluster-agent-8597895bd5-tvbc6        1/1     Running   0          12h   10.42.0.19   2603-900a-2100-79da-0000-0000-0000-102e.inf6.spectrum.com   <none>           <none>
cattle-cluster-agent-8597895bd5-vbr2t        1/1     Running   0          12h   10.42.0.20   2603-900a-2100-79da-0000-0000-0000-102e.inf6.spectrum.com   <none>           <none>
```


