## 配置
export ANSIBLE_HOST_KEY_CHECKING=False

## 产生密钥
ssh-keygen -t rsa -b 2048 -P "" -f /root/.ssh/id_rsa


## 
- `/etc/ansbile/hosts`

```ansbile
[kvm_hosts]
192.168.2.55  ansible_user=root ansible_ssh_pass="1q2w3e4R"
#192.168.2.17  ansible_user=root ansible_ssh_pass="yglzgat"
192.168.2.223  ansible_user=root ansible_ssh_pass="111111"
192.168.2.99  ansible_user=root ansible_ssh_pass="111111"
192.168.2.41  ansible_user=root ansible_ssh_pass="111111"
192.168.2.73  ansible_user=root ansible_ssh_pass="111111"
192.168.2.189  ansible_user=root ansible_ssh_pass="111111"
192.168.2.175  ansible_user=root ansible_ssh_pass="111111"
```

## 设置
```
ansible kvm_hosts -m  authorized_key -a "user=root key='{{ lookup('file', '/root/.ssh/id_rsa.pub') }}'"
```