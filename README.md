# Ansible role: Zint

- Install Zint's build prerequisites
- Build and Install Zint from source on Ubuntu

## Molecule Setup

- refer to setup instructions for basic test running: [molecule-setup](https://git.acromedia.com/mmccann/molecule-setup/blob/master/README.md)
- after setting up your virtual environment and installing dependencies ...

```bash
$ MOLECULE_DISTRO=ubuntu1604 molecule test --destroy=never
```

- log into the container and view changes

```bash
$ molecule login
```

__Variations of MOLECULE_DISTRO__ 

    ubuntu1604
    ubuntu1804

__running the full test suite__

```bash
$ tox
```

## Requirements

* Ubuntu LTS (14.04 or newer)

## Role Variables

See example playbook.

## Dependencies

None

## Example Playbook

    - hosts: servers
    - roles:
        - name: Install Zint from source
          role: acromedia.zint
          zint_version: 2.4.2
          zint_source: "https://github.com/downloads/zint/zint/zint-{{ zint_version }}.tar.gz"
          zint_source_checksum: 'sha256:76547faaba0bfbea43733ab324e498863ebf21fc9a2e5db93512739d661a2b3a'
      tags:
        - zint

## License

GPLv3

## Author Information

Acro Media Inc.
https://www.acromedia.com/
