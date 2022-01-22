
##### List tags in the playbook
```
ansible-playbook --list-tags playbooks/site.yml
```

##### Running a playbook but targeting specific tags
```
ansible-playbook --tags db playbooks.yml
ansible-playbook --tags redhat playbooks/site.yml
ansible-playbook --tags apache playbooks/site.yml
```

