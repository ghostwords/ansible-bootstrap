# Ansible Bootstrap

Used with Ubuntu 14.04 on Digital Ocean. Uses git submodules; clone with `--recursive`.

1. Create a file called `hosts` in the checkout folder and populate it with server IP(s).

2. Configure variables in [group_vars/all](group_vars/all).

3. Run `ansible-playbook bootstrap.yaml` to create an admin user and reconfigure SSH on the hosts.

4. If you set `sshd_port` in step 2 to something other than 22, now is the time to update `remote_port` in [ansible.cfg](ansible.cfg) to match.

5. Run `ansible-playbook main.yaml --ask-become-pass` to finish setting up the hosts.
