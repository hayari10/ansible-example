# Ansible Example

> Manage multiple environments using Ansible

## Quickstart

1. Clone this repository:

    ```
    git clone https://github.com/mbigras/ansible-example
    cd ansible-example
    ```

1. Start a Vagrant machine for `site1` in the `dev` environment:


    ```
    vagrant up /site1/
    ```

    * Each environment can contain multiple sites.
    * Each site can contain multiple machines.

1. Run an Ansible adhoc command:


    ```
    ansible -i dev.ini -m ping
    ```

    This command uses the following options:

    * `-i` - the Ansible inventory. The development, quality assurance, and production environments are organized and isolated into the separate files.
    * `-m` - the Ansible module to execute. This command executs the Ansible [Ping module](https://docs.ansible.com/ansible/2.3/ping_module.html). It's not an ICMP ping. This is just to check if Ansible is working.

1. Run an Ansible playbook:

    ```
    ansible-playbook -i dev.ini playbooks/ping.yml
    ```
