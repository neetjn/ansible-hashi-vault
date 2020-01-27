# ansible-hashi-vault

Ansible playbook for setting up and provisioning a hashi vault instance.

This ansible playbook will install docker if not done so already, and any other necessary packages or modules. This playbook also supports NGINX proxying if a host is specified in the NGINX host group.

### Variables

Playbook inventory variables can be found in `groupvars/all.yml`.

> **vault_port**: Port for NGINX to bind to.

### Use

Clone the repository,
```bash
git clone https://github.com/neetjn/ansible-hashi-vault.git
```

Run the playbook,
```bash
ansible-playbook playbook.yml
```

Optionally, if you would like to configure a remote ystem:
* Replace the placeholder host in the `hosts` inventory file.
* Uncomment the `ansible-ssh-user` and `ansible-ssh-pass` variables from your group variables.
* Update them accordingly with login credentials for your remote machine.

Then run your playbook,

```bash
ansible-playbook playbook.yml -i hosts
```

Additionally if you would like to setup NGINX, add `--extra-vars "vault_host=mydomain.com"` to then end of your ansible-playbook command.

---

Copyright (c) 2019 John Nolette Licensed under the MIT license.

