[![CI](https://github.com/de-it-krachten/ansible-role-grype/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-grype/actions?query=workflow%3ACI)


# ansible-role-grype

Installs grype, a vulnerability scanner for container images and filesystems<br>
https://github.com/anchore/grype<br>



## Dependencies

#### Roles
None

#### Collections
- community.general
- ansible.posix

## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- CentOS 7
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- AlmaLinux 9
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Fedora 35
- Fedora 36

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# Github CLI - API
grype_api: https://api.github.com/repos/anchore/grype

# Github CLI - repo
grype_repo: https://github.com/anchore/grype

# Lookup table for architecture
grype:
  architecture:
    x86_64: amd64
  system:
    Linux: linux
    Darwin: darwin

# Version of the CLI to install
grype_version: latest

# Location/ownership/permissions of the binary
grype_path: /usr/local/bin/grype
grype_owner: root
grype_group: root
grype_mode: '0755'
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'grype'
  hosts: all
  become: "yes"
  tasks:
    - name: Include role 'grype'
      ansible.builtin.include_role:
        name: grype
</pre></code>
