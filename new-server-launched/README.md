
## Launched new server for disaster-recovery for linux 
### First create the virtual-instance from ibm-cloud
### Install the ansible in vm
```bash
cd /opt
apt install ansible
```
### Then clone the iptor-platform
```bash
cd /opt/ansible
git clone https://gitlabiptor.iptor.com/iptor-com-cloud/iptor-platform.git

```
### After this in vm install bacula
#### first change the directory
```bash
cd /opt/ansible
```
### Install the bacula from ansible-playbook
```bash
ansible-playbook bacula-client.yaml
```
> :point_right: there are some default parameter that are common for all the clients 
### Add new client with basic requirements in host server
```bash
vi ansible/roles/bacula-server-configuration/defaults/main.yaml  
```
```yaml
---
sftp01:
    name: sftp01
    bacula_client: ipt-fr-sftp-01-fd
    bacula_client_server_name: sftp01
    bacula_fd_port: 9102
    client_address: 10.204.68.51                                    #  It is the client Ip address
    filset_include_dir: "/etc /home /var/ /opt /root /usr /media /mnt"  # This files are restored
    filset_exclude_dir: "/var/lib/docker /var/lib/bacula"
    iqdn: iqn.2006-06.com.quadstor.vtl.sftp01.drive1                # This is VTL drive
    full_backup_schedule: "Full sun at 01:50"
    incremental_backup_schedule: "Incremental mon-sat at 01:50"
    backup_forcefully: false
    OS_TYPE: linux                                                  # It's different from other OS
```
### Run the ansible-playbook -
```bash
ansible-palybook bacula-server-configruation.yaml
```

### Check the client in machine
``bash
bconsole
```
```bash
st client
```
