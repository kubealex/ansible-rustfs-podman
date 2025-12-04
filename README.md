ansible-rustfs-podman
=========

This is a quick and dirty role to instantiate a Podman based RustFS [https://rustfs.com/](https://rustfs.com/) instance for dev/test purposes.

Role Variables
--------------

| *variable* | *description* | *default* |
|-----------------------|---------------------------------------------------|-------------- |
| rustfs_api_port        | Sets up the listening port for bucket management  | 9000          |
| rustfs_console_port    | Sets up the listening port for rustfs console      | 9001          |
| rustfs_server_domain     | Sets up the external rustfs domain                   | N/A  |
| rustfs_root_user       | Sets the root user name                           | rustfsadmin   |
| rustfs_root_password   | Sets the root user password                       | rustfsadmin     |
| rustfs_configure_ssl  | Configure SSL for RustFS connections               | true          |
| rustfs_cert_path       | Path for RustFS certificate                        |               |
| rustfs_key_path        | Path for RustFS key                                |               |
| rustfs_ca_path        | Path for RustFS CA                                |               |
| rustfs_console_enable        | Enable RustFS Console                               | true              |

Dependencies
------------

*containers.podman* and *ansible.posix* collections are required to run the modules, install them running:

    ansible-galaxy install -r requirements.yml

Example Playbook
----------------

Use this requirements.yml to setup your dependencies:

    ---
    collections:
      - community.general
      - ansible.posix
    roles:
      - name: ansible-rustfs-podman
        src: https://github.com/kubealex/ansible-rustfs-podman.git

Sample usage with default settings:

    - hosts: podman_host
      roles:
        - ansible-rustfs-podman

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
