# Personal ansible playbooks 

This repo contains a few playbooks that I use to setup my computers

## Usage

I'm not well-versed in Ansible, but I use these playbooks as follows:

```sh
ansible-playbook -i <ssh host>, playbooks/<playbook>.yml
```

If the playbook requires to clone a git repo, the ssh agent can be forwarded using:

```sh
ansible-playbook -i <ssh host>, --ssh-extra-args='-A' playbooks/<playbook>.yml
```

If a task also requires root permissions (become), `-K` can be used to specify the password:


```sh
ansible-playbook -i <ssh host>, -K playbooks/<playbook>.yml 
```

Or a combination of both use cases:

```sh
ansible-playbook -i <ssh host>, --ssh-extra-args='-A' -K playbooks/<playbook>.yml
```

I'm not using an actual inventory because I'm not in a server context. I run the playbooks on mobile devices or dispoasble virtual machines that have no permanent IP addresses.
