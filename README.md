Ansible Role: ansible_role_waitfor_pkgmgmt
=========

An Ansible role that wait for packagemanagemt processes. Can be included in playbooks/roles if there is a need to check for apt/yum/etc. processes before continuing with other tasks.
This role should support the following Linux distributions.

<ul>
<li>Fedora
<li>CentOS
<li>Red Hat Enterprise Linux
<li>Debian
<li>Ubuntu
</ul>

Requirements
------------

No special requirements is needed for the role.

Role Variables
--------------

Available variables are listed below, along with default values where applicable (see defaults/main.yml):


    ansible_role_waitfor_pkgmgmt_retries: 30

Number of retries before the role fails.

    ansible_role_waitfor_pkgmgmt_delay: 10

Delay in seconds between retries.

Dependencies
------------

This role has no external dependencies.

Example Playbook
----------------


    - hosts: servers

      vars:
        ansible_role_waitfor_pkgmgmt_retries: 60
        ansible_role_waitfor_pkgmgmt_delay: 10

      tasks:

        - name: import the ansible_role_waitfor_pkgmgmt to be executed before other tasks
          ansible.builtin.import_role:
            name: ansible_role_waitfor_pkgmgmt

        - name: Hellorld!
          debug:
            msg: Hellorld!



License
-------

MIT

Author Information
------------------

Mattias Jonsson