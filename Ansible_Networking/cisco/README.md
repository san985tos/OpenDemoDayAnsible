
# CISCO playbooks

## Check inventory
```
$ ansible-navigator inventory
$ ssh rtr1
	$ show version
```

## Verbose execution of playbook
```
$  ansible-navigator run playbook.yml --mode stdout
```

Just check what will be change

```
$ ansible-navigator run playbook.yml --mode stdout --check -v
```


## Ansible Facts

Checking the documentation

```
$ ansible-navigator
	:doc debug
	:doc cisco.ios.facts
```

Executing facts.yml, when facts.yml has 1 line only

```
$ ansible-navigator run facts.yml
```

The playbook

```
---
- name: gather information from routers
  hosts: cisco
  gather_facts: no
  tasks:
    - name: gather router facts
      cisco.ios.facts:}
```
	      
Adding more lines in the yaml, then rerun with "--mode stdout"

```
$ ansible-navigator run facts.yml --mode stdout
```

The playbook

```
---
- name: gather information from routers
  hosts: cisco
  gather_facts: no
  tasks:
    - name: gather router facts
      cisco.ios.facts:
    - name: display version
      debug:
	msg: "The IOS version is: {{ ansible_net_version }}"
    - name: display serial number
      debug:
	msg: "The serial number is:{{ ansible_net_serialnum }}"
		
```
