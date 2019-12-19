# etcd-ansible
Create etcd cluster with etcdadm via ansible

## Usage

### Installation

`inventory/group_vars/all.yml` Configurations:

```yaml
# download etcdadm binary archive package
# if you want to download from local filesystem, this parameter is file path, such as "/root/etcdadm-v0.1.2.tar.gz".
# if you want to download from http(s) server, this parameter is http(s) url, such as "http://x.x.x.x/etcdadm-v0.1.2.tar.gz".
etcdadm_release_url: ""
etcdadm_version: v0.1.2
etcdadm_debug: true
etcdadm_install_dir: "/opt/bin"
etcdadm_certs_dir: "/etc/etcd/pki"

# etcdadm download etcd release package from this url.
# if empty, etcdadm download etcd from https://github.com/coreos/etcd/releases/download.
etcd_release_url: ""
# etcdadm download the specified version etcd release package.
etcd_version: 3.3.18
```

`ansible-playbook -i inventory/hosts.ini deploy.yml`

### Uninstall

`ansible-playbook -i inventory/hosts.ini reset.yml`