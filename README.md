# ansible-role-consul

Install Hashicorp Consul, production mode on multiple servers

*NOTE* The role is capable to run idempotent keeping already generated certificates and secrets. This is an `alpha` release, please don't use it in production.

## Role Variables

```yaml
# Default action (install|delete)
action: install

# Consul version to download and its checksum
consul_version: "1.7.1"
consul_sha256: "sha256:09f3583c6cd7b1f748c0c012ce9b3d96de95a6c0d2334327b74f7d72b1fa5054"

# Datacenter name 
consul_datacenter: dc1
consul_data_dir: /opt/consul

# Use TLS for consul
consul_use_tls: false

# Generate certificates
consul_tls_generate: true

# Load provided certificates:
# WARNING: consul_tls_server_file and consul_tls_key_file MUST BE define once per host
# in inventory or using host_vars
consul_tls_provided: false
consul_tls_ca_file: ""
consul_tls_server_file: ""
consul_tls_key_file:  ""

# Enable use of ACL
consul_use_acl: false
```

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

```yaml
    - hosts: servers
      roles:
         - { role: consul-ha }
```

## License

GPL-V3
