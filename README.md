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

2603-900a-2100-79da-0000-0000-0000-102e:~ # kubectl get pods -n cattle-system
NAME                                                              READY   STATUS      RESTARTS   AGE
apply-system-agent-upgrader-on-2603-900a-2100-79da-0000-0-79f6k   0/1     Completed   0          7m17s
cattle-cluster-agent-8597895bd5-tvbc6                             1/1     Running     0          17m
cattle-cluster-agent-8597895bd5-vbr2t                             1/1     Running     0          7m18s
rancher-webhook-586f888bb-47bq9                                   1/1     Running     0          7h11m
system-upgrade-controller-5fb67f585d-7wqgd                        1/1     Running     0          7h12m
```

