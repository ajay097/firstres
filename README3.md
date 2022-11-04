## bacula-restore via automation


### Clone Iptor-platform repo -

```bash
git clone https://gitlab.int.iptor.com/iptor-cloud/iptor-platform.git
```

### Change the directory -
```bash
cd iptor-platform
```

### Run the ansible playbook

```bash
ansible-playbook bacula-restore.yaml
```

> :point_right: **there are some default parameter that are common for all the clients for restore** 

### Setup the below code in directory -

```bash
vi ansible/roles/bacula-restore/defults/main.yml
```
### Set the default parameter in the above file-
``` yaml
---
bacula_client: ipt-fr-cpanel-01-fd
bacula_client_name: CPANEL01
restore_client: ipt-fr-cpanel-01-fd
jobid: 1441
```

 ### Now run the ansible-playbook -
 ```bash
 ansible-playbook bacula-restore.yaml
```

### Get the bconsole -
```bash
bconsole
```

### Check the status -
```bash
st dir
```
### Check messages-
```bash
messages
```
