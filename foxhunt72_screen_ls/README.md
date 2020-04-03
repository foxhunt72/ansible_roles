Role Name
=========

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

---
- hosts: all
  tasks:
  - name: create screenls
    include_role:
      name: foxhunt72_screen_ls
    vars:
      screen_username: root
      screen_filename: /root/screen-ls.sh
      screen_cron_minute: "*/3"
      screen_uptime: 30m
      screen_program:
        - name: proef1
          script: /root/bin/proef1.sh
          time: 5m
          exclusive: proef1,proef2
        - name: proef2
          script: /root/bin/proef2.sh
          time: 1d
          exclusive: proef1,proef2
        - name: proef3
          script: /root/bin/proef3.sh
          uptime: 3h

# second example
- name: create screenls
  include_role:
    name: foxhunt72_screen_ls
  vars:
    screen_username: sabnzbd
    screen_filename: /home/sabnzbd/screen-ls.sh
    screen_cron_minute: "*/3"
    screen_uptime_min: 15
    screen_program:
      - name: start_sabnzbd
        script: /home/sabnzbd/start_sabnzbd.sh


License
-------

GPL-v3

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
