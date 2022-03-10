ansible-role-container-service 
=========

Ansible role to setup container-based systemd-services.


Requirements
------------

This role was created for Ubuntu 20.04.


Role Variables
--------------

Required variables to be set on command-line or in the playbook are:

`podman_os` needs to be set to the correct linux-distribution and version. Please check https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/ 


```yaml
containers:
  - name: <name of the container>
    image: <image>
    exposed_ports: <Exposed range of ports e.g. 8080, 8080-8089, or list of ports>
    published_ports: <list of port mappings published to the host e.g. 8080:80>
    volumes: 
    - hostpath:  <path of the volume on the host>
      mountpoint: <mountpoint inside the container>
    env:
      <varibale-name>: <value>
```



Example Playbook
----------------

This role can be easily used in a playbook like this: 

```yaml
- hosts: froxlor-servers
  roles:
      - ansible-role-container-service 
```

License
-------
GNU GENERAL PUBLIC LICENSE VERSION 3

Author Information
------------------
[blog.retter.jetzt](https://blog.retter.jetzt)
