# ansible-role-consul

Install Hashicorp Consul, production mode on multiple servers

## Role Variables

TODO

## Tags

Supported tags are:

- install
  - will download the specified version of consul and perform installation of the binary and systemd service on the system
- prepare
  - will create user,groups and all needed directories
- configure
  - will replace configuration file
- tls
  - will generate TLS certificates, exclude this in case you want to reconfigure or update your host without loosing old TLS setup

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: consul-ha }

## License

GPL-V3
