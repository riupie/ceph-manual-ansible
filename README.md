### HOWTO
#### PREREQUISITES
```
1. Ansible 2.9
2. Edit group_vars/all.yml.

```

#### QUICK START DEPLOYMENT
```bash
ansible-playbook -i host site.yml
```

#### STEP BY STEP DEPLOYMENT

##### Configure NTP client, update & upgrade packages, install UCA repository (depend on group_vars/all.yml configuration)
```bash
ansible-playbook -i host site.yml -t predeploy
```

##### Install and add monitor nodes
```bash
ansible-playbook -i host site.yml -t bootstrap-monitor
```

##### Install and add manager nodes
```bash
ansible-playbook -i host site.yml -t bootstrap-manager
```

##### Install osd packages only
```bash
ansible-playbook -i host site.yml -t bootstrap-osd
```

##### Create OSD disk
```bash
ansible-playbook -i host site.yml -t create-osd
```

##### Install Ceph Dashboard
```bash
ansible-playbook -i host site.yml -t enable-dashboard
```
