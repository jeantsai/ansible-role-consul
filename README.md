Ansible Role Consul
=========

An ansible role to install Consul cluster with TLS and ACL

Requirements
------------

A python environment is needed by this project. And it is better if virtualenv, pyenv or other similar tool is leveraged.


Role Variables
--------------

Variable                   | Default Value                        | Description
---------------------------|--------------------------------------|----------------------------------------
consul_user                |  consul                              | name of the user to run consul
consul_group               |  consul                              | group of the user to run consul
consul_bin_dir             |  /usr/local/bin                      | folder holding consul executables
consul_data_dir            |  /var/lib/consul                     | folder holding consul data
consul_conf_dir            |  /etc/consul.d                       | folder holding consul config files
consul_cert_dir            |  ssl under conf dir                  | folder holding certificates and relevant key files
consul_run_dir             |  /run/consul                         | folder holding consul runtime info files
consul_systemd_restart_sec |  15                                  | delay before the restarting to avoid 'too short' error
consul_ca_cert_file        |  consul-agent-ca.pem                 | file name of CA certificate
consul_ca_key_file         |  consul-agent-ca-key.pem             | file name of the key of CA certificate
consul_server_cert_file    |  <dc>-server-<domain>-0.pem          | file name of server certificate
consul_server_key_file     |  <dc>-server-<domain>-0-key.pem      | file name of the key of server certificate
override_ca_cert           |  false                               | Whether to override existing CA certificate
override_server_certs      |  false                               | Whether to override existing server certificates

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------



Example Playbook
----------------

  ---
  - hosts: consul_server
    roles:
      - jeantsai/ansible-role-consul


License
-------

GPL v3
