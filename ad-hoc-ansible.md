```
ansible localhost -m ping 
```

##### Test Ansible is working
```
ansible all --key-file ~/.ssh/ansible -i inventory -m ping
```

##### Create ansible config file
vim ansible.cfg
``` 
[defaults]
inventory = inventory 
private_key_file = ~/.ssh/ansible
```

##### Ansible command simplified (Other parameters from ansible.cfg file)
```
ansible all -m ping
```

###### List all of the hosts in the inventory
```
ansible all --list-hosts
```

##### Gather facts about your hosts
```
ansible all -m gather_facts
```

##### Gather facts about your hosts, but limit it to just one host
```
ansible all -m gather_facts --limit 172.16.250.132
```

### Run ansible with elevated previliges

##### Tell ansible to use sudo (become)
```
ansible all -m apt -a update_cache=true --become
```

##### Install a package via the apt module
```
ansible all -m apt -a name=vim-nox --become
```

###### Install a latest package via the apt module
```
ansible all -m apt -a "name=vim-nox state=latest" --become
```

##### Upgrade all the package updates that are available
```
ansible all -m apt -a upgrade=dist --become
```

**Note**: If sudo needs a password, then pass the parameter --ask-become-pass
