# start-vm-playbook

Experiment on a clone of [start-vm](https://github.com/shakfu/start-vm) as an ansible [playbook](http://docs.ansible.com/ansible/playbooks.html).

# Installation

- Install Ansible locally
- Create a VM (or many!) (preferably ubuntu 16.04 for this experiment)
- Make sure the VM has a working `/usr/bin/python` binary.
- Clone this repository
- Change the content of the `hosts` file to contain the ip address of the target machines.
- run the following command: `ansible-playbook -i hosts site.yml`

# How it maps to start-vm

The main idea is to try and replicate start-vm's provided `base.yml` sample as accurate as possible. Here's how entries in start-vm's `base.yml` map to this playbook

```
base.yml -> site.yml
sections definition -> roles definition
debian_packages -> apt task present state
pre-install -> standard task (random module)
purge -> apt task absent state
post-install -> standard task (random module)
python_packages -> pip task
```

# What was not done

Quite a few things were left out since this is merely an experiment, most notably the configurations for different tools installed.
