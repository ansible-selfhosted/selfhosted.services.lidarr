[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Copier](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/copier-org/copier/master/img/badge/badge-grayscale-inverted-border.json)](https://github.com/copier-org/copier)
[![Podman Badge](https://img.shields.io/badge/Podman-892CA0?logo=podman&logoColor=white)](https://podman.io/)
[![Hatch project](https://img.shields.io/badge/%F0%9F%A5%9A-Hatch-4051b5.svg)](https://github.com/pypa/hatch)
![CI](https://github.com/ansible-selfhosted/selfhosted.services.lidarr/actions/workflows/ci.yml/badge.svg)
[![Ansible](https://img.shields.io/badge/Ansible-Molecule-EE0000?style=plastic&logo=ansible&logoColor=white)](https://github.com/ansible/molecule)

<!-- BEGIN_ANSIBLE_DOCS -->

# Ansible Role: [lidarr](https://wiki.servarr.com/en/lidarr)

A role to deploy Lidarr using rootless Podman with systemd

## Role Requirements

- none

*Refer to services collection for general requirements*

## Role Arguments

|Option|Description|Type|Required|Default|choices|
|---|---|---|---|---|---|
|lidarr_additional_options|List of additional key=value for the quadlet container<br>ex: - "Network=custom.network"<br>Can also be used to leave comments by preceding with a '#'|list|False|[]|
|lidarr_config_label|The labels for to the lidarr config directory<br>Comma separated values (ex: rw,Z)|str|False||
|lidarr_config_path|The path to the lidarr configuration directory|str|False|~/.config/lidarr/|
|lidarr_data_label|The labels for to the lidarr data directory<br>Comma separated values (ex: rw,Z)|str|False||
|lidarr_data_path|The path to the lidarr data directory<br>It is recommended to share the same data directory with other media managing services|str|False|~/.local/share/containers/storage/media|
|lidarr_puid|The user id to run the inside the lidarr container|int|False|1000|
|lidarr_pgid|The group id to run the inside the lidarr container|int|False|1000|
|lidarr_timezone|The timezone for the lidarr service|str|False|Etc/UTC|
|lidarr_version|The version of Lidarr to use|str|False|latest|<ul><li>latest</li><li>develop</li><li>nightly</li></ul>
|lidarr_web_port|The port for the web server|int|False|8686|


## Example Playbook

```
- hosts: all
  tasks:
    - name: Importing lidarr role
      ansible.builtin.import_role:
        name: selfhosted.services.lidarr
      vars:
```

## License

This project is licensed under the [MIT License](LICENSE)


⊂(▀¯▀⊂)

<!-- END_ANSIBLE_DOCS -->
