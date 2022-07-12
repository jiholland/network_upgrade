Role Name
=========

Upgrade OS, check compliance, upload OS or schedule the upgrade (see examples) for Cisco Catalyst and Nexus devices. 

Requirements
------------

[Cisco IOS Collection](https://galaxy.ansible.com/cisco/ios)<br>
[Cisco NXOS Collection](https://galaxy.ansible.com/cisco/nxos)<br>
[Ansible Posix Collection](https://galaxy.ansible.com/ansible/posix)

Role Variables
--------------

defaults:
- tftp\_server

vars:
- compliant\_os\_version
- compliant\_os\_file

Dependencies
------------

None.

Example Playbook
----------------

    ---
    - name: upgrade os to compliant version
      hosts: "{{ target }}"
      gather_facts: false

      roles:
        - network_upgrade


Run playbook in check-mode to verify compliance without making any changes:

    ansible-playbook playbook_network_upgrade.yml -e "target=switch01" --check

Use tag **upload** to upload without installing:

    ansible-playbook playbook_network_upgrade.yml -e "target=switch01" --tags upload

Use tag **schedule** to schedule the installation:

    ansible-playbook playbook_network_upgrade.yml -e "target=switch01" --tags schedule

Run playbook without any tags to install immediately.


License
-------

BSD

Author Information
------------------

Jørn Ivar Holland
