#### TO add new node in bacula-server 
### Firstly clone the gitlab repo by following commad - 
```
bash
git clone https://gitlabiptor.iptor.com/iptor-com-cloud/iptor-platform.git
````

### Go to the repo directory - 
```
bash
cd iptor-platform/
```

### Run the ansible-playbook -
```
bash
ansible-playbook bacula-server configuration.yaml
```

### Add new node/client then follow below steps -

> :point_right: there are some default parameter that are common for all the clients 

### Add new client with basic requirements -
```
bash
vi ansible/roles/bacula-server-configuration/defaults/main.yaml  
```

```
yaml
---
BACULA_CLIENTS:
  smtp03:
    name: SMTP03
    bacula_client: smtp03.iptor.cloud-fd
    bacula_client_server_name: smtp03
    bacula_fd_port: 9102
    backup_client_name: SMTP03
    client_address: 10.206.4.29
    filset_include_dir: "/etc /home /var/ /opt /root /usr /media /mnt"
    filset_exclude_dir: "/var/lib/docker /var/lib/bacula /var/data/kafka"
    iqdn: iqn.2006-06.com.quadstor.vtl.smtp.drive1
    full_backup_schedule: "Full sun at 02:35"
    incremental_backup_schedule: "Incremental mon-sat at 02:35"
    backup_forcefully: false

```
### Run the ansible-playbook -
```
bash
ansible-palybook bacula-server-configruation.yaml
```

### Now check the client - 
### First change the directory -
```
bash
cd /etc/bacula/conf.d
```

### now see the client -
```
bash
 ls -l
```
