# ansible_install_elastic_stack
Ansible playbook for elastic stack

##
Elastic stack version changes frequently so that I need to tool for easy install to my local VirtualBox.

## Precondition
1. JDK must be installed
2. Ansible must be installed: https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html
3. Root permission

### Install Elasticsearch
```shell
ansible-playbook -i hosts/es-servers -k -K install/install_es.yml -e "server=es-servers" -v
```
### Install Kibana
```shell
ansible-playbook -i hosts/kibana-servers -k -K install/install_kibana.yml -e "server=kibana-servers" -v
```

### Start and Stop, Restart
```shell
ansible-playbook -i hosts/servers -k -K install/start_es.yml -e "server=es-servers  option=start" -vvvv
```
```shell
ansible-playbook -i hosts/servers -k -K install/start_kafka.yml -e "server=es-servers  option=start" -vvvv
```
option= start, stop, restart