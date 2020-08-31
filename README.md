### HOWTO
#### PREREQUISITES
```
1. Ansible 2.9
2. Edit group_vars/all.yml.
3. Edit hosts
```

#### QUICK START DEPLOYMENT
```bash
ansible-playbook -i host site.yml
```

#### STEP BY STEP DEPLOYMENT

##### 1. Configure NTP client, update & upgrade packages, install UCA repository (depend on group_vars/all.yml configuration)
```bash
ansible-playbook -i host site.yml -t predeploy
```

##### 2. Install and add monitor nodes
```bash
ansible-playbook -i host site.yml -t bootstrap-monitor
```

##### 3. Install and add manager nodes
```bash
ansible-playbook -i host site.yml -t bootstrap-manager
```

##### 4. Install osd packages only
```bash
ansible-playbook -i host site.yml -t bootstrap-osd
```

##### 5. Create OSD disk
```bash
ansible-playbook -i host site.yml -t create-osd
```

##### 6. Install Ceph Dashboard
```bash
ansible-playbook -i host site.yml -t enable-dashboard
```
