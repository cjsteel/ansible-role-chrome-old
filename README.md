
ansible-role-apt_install
=======================

An Ansible role to install and manage apt_install browser installations.


Requirements
------------

### Ubuntu 16.04

```shell
sudo apt-get install libjpeg62
```


Options
-------

- Matlab (only needed to run FS-FAST, the fMRI analysis stream)



Issues
------


Role Variables
--------------

### roles/apt_install/defaults/main.yml

```yaml
---
# defaults file for ansible-role-apt_install

apt_install_state             : 'present'            # 'present' # 'absent'
apt_install_apt_key_state     : '{{ apt_install_state }}' # 'present' # 'absent'
apt_install_apt_repo_location : 'sources_list_d'     # sources_list # location of apt_sources entry

# packages and plugins

apt_install_apt_packages         : 'google-apt_install-stable'

# key_ids

apt_install_google_linux_package_signing_key_id       : '7FAC5991'
apt_install_google_linux_package_signing_authority_id : 'D38B4796'

# key and entry

apt_install_source_signing_key   : 'https://dl-ssl.google.com/linux/linux_signing_key.pub'
apt_install_apt_source_entry     : 'deb [arch=amd64] https://dl.google.com/linux/apt_install/deb/ stable main'
apt_install_sources_list_d_entry : 'https_dl_google_com_google-apt_install'  # .list is appended by the module
```


Dependencies
------------

* none at this time


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
    - hosts: apt_install
      roles:
         - { role: cjsteel.ansible-role-apt_install, apt_install_state: 'present' }
```



## Role Testing

### Locally using vagrant

```shell
mkdir .vagrant/synced
vagrant up
vagrant ssh -- -X
google-apt_install-stable
exit
vagrant destroy
```



## License

Various, MIT



## Author Information

Christopher Steel on behalf of ACElabs  
Systems Administrator  
McGill Centre for Integrative Neuroscience  
Montreal Neurological Institute  
E-mail: christopherDOTsteel@mcgill.ca  
[mcin-cnim.ca](http://mcin-cnim.ca/)    
[theneuro.ca](http://www.mcgill.ca/neuro/)   

## Open Science



The Neuro has adopted the principles of Open Science. We are inspired by the likes of the Allen Institute for Brain Science, the National Institutes of Health's Human Connectome project, and the Human Genome project. For additional information please see [open science at the neuro]( https://www.mcgill.ca/neuro/open-science-0).





![MCIN](imgs/mcin-logo-brain-140x116.png)          ![neuro](imgs/neuro-logo-160x116.png)  
