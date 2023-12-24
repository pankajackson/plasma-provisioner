# README

Provision Installed Plasma Desktop. Currently supported Debian based OS.

### What is this repository for?

- Install and configure development Workstation in just one command
- Based on KDE Plasma 5 (Kubuntu)
- Tested with Ubuntu 21.XX and 22.XX LTS/Non LTS
- Requires root access to run the script

### How do I get set up?

- Usage:

  ```bash
  sudo apt install python3-full python3-pip python-is-python3
  sudo pip install ansible
  ansible-playbook playbooks/plasma-provisioner.yml -c local -i localhost, --ask-become-pass
  ```

- for Development and testing

  ```bash
  vagrant up
  ```

- Other guidelines

### Who do I talk to?

- Repo owner or admin
- Other community or team contact
