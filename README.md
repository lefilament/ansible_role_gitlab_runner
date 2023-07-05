GitLab Runner Lab
=================

This role lets deploy a GitLab Runner.
The main repo for this role is on [Le Filament GitLab](https://sources.le-filament.com/lefilament/ansible-roles/gitlab_runner.git)

Requirements
------------

None

Role Variables
--------------

Variables from vars directory :
* gitlab_runner_gpg_key_url: GitLab Runner GPG key to be added to apt_key
* gitlab_runner_packages_url: GitLab Runner packages URL to retrieve packages from

Dependencies
------------

This role has no dependencies per-se, however, it is foreseen to use other roles from Le Filament on the same server :
* init_server for initial server configuration (and in particular SSHD configuration) - https://sources.le-filament.com/lefilament/ansible-roles/init_server
* security to securize GitLab server (iptables, auditd, fail2ban) - https://sources.le-filament.com/lefilament/ansible-roles/server_security

Example Playbook
----------------

    - hosts: gitlab
      become: true
      roles:
      - { role: gitlab_runner, tags: gitlab_runner }

License
-------

AGPL-3

Author Information
------------------

Le Filament (https://le-filament.com)
