# Ansible "Cron" module bug report

**Expected Result: (run with 2.9.11)**
- should have 3 cron tasks being defined in target output file

```
% pip install ansible==2.9.11

% ansible --version

ansible 2.9.11

% ansible-playbook --connection=local --inventory localhost, playbook.yml

% cat /tmp/demo-cronfile

#Ansible: demo task 3
* * * * * root echo task 3
#Ansible: demo task 1
* * * * * root echo task 1
#Ansible: demo task 2
* * * * * root echo task 2
```

**Actual Result: (run with 2.9.12)**
- Only last cron task being written into target output file

```
% pip install ansible==2.9.12

% ansible --version

ansible 2.9.12

% ansible-playbook --connection=local --inventory localhost, playbook.yml

% cat /tmp/demo-cronfile

#Ansible: demo task 3
* * * * * root echo task 3
```
