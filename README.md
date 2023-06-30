# Ansible test scripts to deploy k8s on Ubuntu 22.04

## Example inventory
### invetories/test/inventory
```
[master]
111.111.111.111

[nodes]
222.222.222.222
333.333.333.333


[all:vars]
ansible_connection="ssh"
ansible_become="yes"
ansible_user="<ubuntu>"
ansible_ssh_private_key_file="<your_private_key>"

```


### invetories/test/group_vars/all
```
all:
    public_ip: "0.0.0.0"
    clustername: "___"
    cidr: "10.245.0.0/16"
    username: "___"
    cert_dir: "/etc/ssl"

reqs:
    docker_version:  #empty is latest without refs If you want a specific version add es example "-19.03.9"
    containerd_version:  #empty is latest without refs. If you want a specific version add es example "-1.3.7"
    
k8s:
    kube_version: "1.27.1"
    k8s_port: "6443"

mlb:
    ips: ["<ip1>","<ip2>"]

    


```