ansible-role-gitlab-ee
======================

This role deploys a gitlab-ee instance and does the following:

* gitlab installation w/ features
* manages gitlab.rb
* manages gitlab-secrets.json
* deploys gitlab ee license
* deploys gitlab host keys
* triggers gitlab reconfiguration

Requirements
------------

* none

Role Variables
--------------

See defaults/main.yml

Dependencies
------------

* none

Example Playbook
----------------

```yaml
  - name: playbook to install gitlab
    hosts: gitlab
    become: yes
    roles:
      - gitlab
```

Additional Information
----------------------

How to test:

```
$ ansible-playbook -i inventories/lab/hosts plays/gitlab.yml --ask-vault-pass --check --diff
$ ansible-playbook -i inventories/tst/hosts plays/gitlab.yml --ask-vault-pass --check --diff
$ ansible-playbook -i inventories/prd/hosts plays/gitlab.yml --ask-vault-pass --check --diff
```

Note:

If you'd like to see any actual diff output during the test run, you need to remove or disable the `no_log` directive in the configure.yml task.

License
-------

GPLv3

Author Information
------------------

Aaron (aaron@0x29a.ch)
