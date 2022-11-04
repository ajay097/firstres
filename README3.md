## bacula-restore via automation


### Clone Iptor-platform repo -

```bash
git clone https://gitlab.int.iptor.com/iptor-cloud/iptor-platform.git
```

### Now change the directory -
```bash
cd iptor-platform
```

### Now run the ansible playbook

```bash
ansible-playbook bacula-restore.yaml
```

> :point_right: **there are some default parameter that are common for all the clients for restore** 

### Now you setup the below code in directory -

```bash
vi ansible/roles/bacula-restore/tasks/backup-bacula.yml
```

``` yaml
---
- name: restoring the job to the other client
  shell: |
    cd /etc/bacula
    bconsole -c bconsole.conf <<END_OF_DATA
    @output /dev/null
    @output /var/log/bacula/{{ bacula_client_name }}-restore-{{ restore_client }}-log.out
    restore jobid={{ jobid }} client={{ bacula_client_name }} restoreclient={{ restore_client }} fileset=FileSet{{ bacula_client_name }} restorejob=RestoreBackup{{ bacula_client_name }} all done yes
    messages
    @output
    END_OF_DATA
```
### Now include backup-bacula.yml in tasks/main.yml
```bash
vi ansible/roles/bacula-restore/tasks/main.yml
```

```yml
---
- name: rendering on backup-bacula.yml
  include_tasks: backup-bacula.yml
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
