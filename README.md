# Ansible Example

> Manage multiple environments using Ansible

## Quickstart

1. Clone this repository:

    ```
    git clone https://github.com/mbigras/ansible-example
    cd ansible-example
    ```

1. Start the `srv1.site1.egfast.com` Vagrant machine for `site1` in the `dev` environment:


    ```
    vagrant up /site1/
    ```

    * Each environment can contain multiple sites.
    * Each site can contain multiple machines.

1. Run an Ansible adhoc command:


    ```
    ansible -i dev.ini site1 -m ping
    ```

    This command uses the following options and argument:

    * `-i` - Ansible inventory. The development, quality assurance, and production environments are organized and isolated into the separate files.
    * `site1` - Pattern for the site to target.
    * `-m` - Ansible module to execute. This command executs the Ansible [Ping module](https://docs.ansible.com/ansible/2.3/ping_module.html). It's not an ICMP ping. This is just to check if Ansible is working.

1. Run an Ansible playbook:

    ```
    ansible-playbook -i dev.ini -l site1 playbooks/ping.yml
    ```

    Gotcha: The `ansible-playbook` command uses the same pattern as the `ansible` command but uses the `-l` flag.

1. Destroy the `srv1.site1.egfast.com` Vagrant machine:

    ```
    vagrant destroy -f /site1/
    ```