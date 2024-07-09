## Welcome to Ansible Pro ##

## Check mode 
``` ansible-playbook playbook.yml --check```
## Check and Diff mode 
``` ansible-playbook playbook.yml --check --diff```

## Syntax check mode
``` ansible-playbook playbook.yml --syntax-check```

## To check ansible.cfg details

``` ansible-config list ```

``` ansible-config view ```

``` ansible-config dump ```


## Ansible Lint to check potential errors

``` ansible-lint playbook.yml ```



``` 
stapp01 ansible_host=172.16.238.10 ansible_user=tony ansible_ssh_pass=Ir0nM@n
stapp02 ansible_host=172.16.238.11 ansible_user=steve  ansible_ssh_pass=Am3ric@ 
stapp03 ansible_host=172.16.238.12 ansible_user=banner  ansible_ssh_pass=BigGr33n
```   



---

- name: "Copy index.html to /opt/itadmin"
  hosts: all
  become: yes
  tasks:
    - name: copy index.html to /opt/itadmin
      copy:
        src: /usr/src/itadmin/index.html
        dest: /opt/itadmin



- name: "Copy index.html to /opt/itadmin"
  hosts: all
  become: yes
  tasks:
    - name: copy index.html to /opt/itadmin
      yum:
        name: httpd
        state: present

      when: ansible_os_family == "Centos"

    - name: copy index.html to /opt/itadmin
      apt:
        name: httpd
        state: present

# =====================================

- name: "Create a blank file"
  hosts: all
  become: yes
  tasks:
    - name: "create a blank file"
      file:
        path: /usr/src/web.txt
        state: touch
        mode: 0644
        owner:
        group: 
























