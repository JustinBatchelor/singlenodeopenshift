preflight-checks
=========

Role to ensure that all requirements to communicate to the Assisted Installer API are/have been met. This role also contains the code need to generate a new token that can be used to authenticate against the Assisted Installer API.  

_**Please note that tokens are only valid for 15 minutes as per the Assisted Installer documentation**_

Requirements
------------

* pull-secret path is defined in `vars.yml` and exists
* token path is defined in `vars.yml` and exists

Role Variables
--------------

N/A

Dependencies
------------

N/A

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
- name: Playbook used during testing of the role preflight-checks
  hosts: localhost
  become: true
  vars_files:
    - '../vars.yml'
  vars_prompt:
    - name: ansible_become_password
      prompt: "Enter your sudo password here"
      private: true
  tasks:
    - name: Include role preflight-checks
      ansible.builtin.include_role:
        name: preflight-checks
```

License
-------

BSD

Author Information
------------------

- Justin Batchelor | Justinrossbatchelor@gmail.com
