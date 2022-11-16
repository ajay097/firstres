
Sir this is for create new server

## Add new client for disaster-recovery for linux 
### First create the virtual-instance from ibm-cloud

### Install the ansible in vm
```bash
cd /opt
apt install ansible
```
### Then clone the iptor-platform
```bash
cd /opt/ansible

git clone -b bacula-server-installation https://inravpra:glpat-1x7bCc6ysAZyvx6miN5k@gitlab.int.iptor.com/iptor-cloud/iptor-platform.git
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

### Add new client with basic requirements -

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
    client_address: 10.204.68.51
    filset_include_dir: "/etc /home /var/ /opt /root /usr /media /mnt"
    filset_exclude_dir: "/var/lib/docker /var/lib/bacula"
    iqdn: iqn.2006-06.com.quadstor.vtl.sftp01.drive1
    full_backup_schedule: "Full sun at 01:50"
    incremental_backup_schedule: "Incremental mon-sat at 01:50"
    backup_forcefully: false
    OS_TYPE: linux
```

### Run the ansible-playbook -
```bash
ansible-palybook bacula-server-configruation.yaml
```

### After this in bacula conf. file add device with defaults parameter
```yaml
---
Device {
  Name = TS-K601
  Drive Index = 0
  Media Type = TS-3100
  Archive Device = /dev/st3
  AutomaticMount = yes
  Autochanger = no
  Always Open = no
  RemovableMedia = yes
  LabelMedia = yes
}
``` 
### Check the cleint in machine
``bash
cd /etc/bacula/conf.d/
```
```bash
ls -l
```

