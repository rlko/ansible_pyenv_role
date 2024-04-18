# Ansible Role: pyenv

## Description

This Ansible role installs and configures `pyenv` for managing Python versions on your systems.

## Requirements

* Ansible >= 2.9
* Python packages on target systems (might be required by `pyenv-installer.sh`)

## Role Variables

* `pyenv_root`: (Optional) Path to the `pyenv` installation directory. Defaults to `/opt/pyenv`.
* `pyenv_deb_packages`: (List) List of Debian/Ubuntu package names required for `pyenv` (e.g., `build-essential`).
* `pyenv_rpm_packages`: (List) List of RPM package names required for `pyenv` (e.g., `gcc`).

## Dependencies

* None

## Example Playbook

```yaml
---
- hosts: all
  become: true  # Required for some installation steps
  roles:
    - role: pyenv
      pyenv_root: ~/.pyenv  # Optional, customize if needed. Defaults to `/opt/pyenv`
```

## Installing the Role

1. Clone or copy this role directory into your Ansible roles directory.
2. (Optional) Modify the role variables (`defaults/main.yml` and `vars/main.yml`) to customize settings like `pyenv_root`, package lists, etc. Since I only added packages for Debian family and Red Hat family.
3. Include the role in your playbook as described in the documentation for your chosen Ansible playbook format.

## License

MIT License

## Author

rlko

## Additional Notes

* System dependencies for `pyenv` installation are on based the pyenv [wiki](https://github.com/pyenv/pyenv/wiki).
* Consider error handling and logging mechanisms in your playbook for a more robust deployment.

