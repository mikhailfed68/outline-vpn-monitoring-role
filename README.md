outline-vpn-monitoring-role
=========

A simple role for adding monitoring infrastructure (Prometheus + Grafana) to the host where you are using [Outline VPN](https://getoutline.org) server.
Optionally, the Node Exporter is also installed.

Requirements
------------

You need the following files in the playbook directory:
- certs/grafana/grafanaCert.crt 
- certs/grafana/grafanaPrivate.key
- services/grafana/grafana.ini

But you can choose not to use them or grafana-piechart-panel plugin, for example:

`
ansible-playbook -i inventories/sandbox/hosts.ini site-monitoring.yml --vault-password-file=vault --skip-tags grafana-https,grafana-config,grafana-plugins
`

Role Variables
--------------


Dependencies
------------


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: common
      gather_facts: yes
      become: yes
      roles:
        - "outline-vpn-monitoring"

License
-------

BSD

Author Information
------------------

Mikhail Fedorov, mikhailfedorov1939@gmail.com


###### For more information, read:
- [Set up Grafana HTTPS for secure web traffic](https://grafana.com/docs/grafana/latest/setup-grafana/set-up-https/)
- [Configure Grafana](https://grafana.com/docs/grafana/latest/setup-grafana/configure-grafana/)
- [Grafana dashboard for Outline Servers](https://gist.github.com/fortuna/ea92f0ac0e7543ed5feea75902880ca0)
- [Node Exporter Full](https://grafana.com/grafana/dashboards/1860-node-exporter-full/)
- [Ansible Prometheus role](https://prometheus-community.github.io/ansible/branch/main/prometheus_role.html)
