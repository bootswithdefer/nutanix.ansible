# Nutanix Ansible Collection - nutanix.ncp
Ansible collections to automate Nutanix Cloud Platform (ncp).

# Building and installing the collection locally
```
ansible-galaxy collection build
ansible-galaxy collection install nutanix.ncp-1.0.0.tar.gz
```
_Add `--force` option for rebuilding or reinstalling to overwrite existing data_

# Included modules
```
ncp_prism_image_info
ncp_prism_image
ncp_prism_vm_info
ncp_prism_vm
```

# Inventory plugin
`ncp_prism_vm_inventory`

# Module documentation and examples
```
ansible-doc nutanix.ncp.<module_name>
```

# Examples
## Playbook to print name of vms in PC
```
- hosts: localhost
  collections:
  - nutanix.ncp
  tasks:
  - ncp_prism_vm_info:
      pc_hostname: {{ pc_hostname }}
      pc_username: {{ pc_username }}
      pc_password: {{ pc_password }}
      validate_certs: False
    register: result
  - debug:
      msg: "{{ result.vms }}"
```
