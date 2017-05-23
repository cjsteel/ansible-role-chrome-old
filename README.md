
ansible-role-chrome
=======================

An Ansible role to install and manage chrome browser installations.


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

### roles/chrome/defaults/main.yml

```yaml
chrome_state             : present # absent, purged
chrome_apt_key_state     : '{{ chrome_state }}'
chrome_apt_repo_location : sources_list_d # sources_list # location of apt_sources entry

# current repo
chrome_source_signing_key   : 'https://dl-ssl.google.com/linux/linux_signing_key.pub'
chrome_apt_source_entry     : 'deb [arch=amd64] https://dl.google.com/linux/chrome/deb/ stable main'
chrome_apt_packages         : 'google-chrome-stable'
chrome_sources_list_d_entry : 'https_dl_google_com_google-chrome'  # .list is appended by the module

# stale repo options, not implemented at this time
chrome_stale_remove               : False # Used to remove stale (old) chrome entries should be removed.
chrome_stale_state                : 'purged' # 'absent' # 'present'
chrome_stale_apt_source_entry     : 'deb [arch=amd64] https://dl.google.com/linux/chrome/deb/ stable main'
chrome_stale_sources_list_d_entry : 'null'
```


Dependencies
------------

* none at this time


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
    - hosts: chrome
      roles:
         - { role: cjsteel.ansible-role-chrome, x: 42 }
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