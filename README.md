# [Ansible role puppet](#puppet)

Install Puppet on your system (Linux).

|GitHub|GitLab|Downloads|Version|Issues|Pull Requests|
|------|------|-------|-------|------|-------------|
|[![github](https://github.com/buluma/ansible-role-puppet/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-puppet/actions/workflows/molecule.yml)|[![gitlab](https://gitlab.com/shadowwalker/ansible-role-puppet/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-puppet)|[![downloads](https://img.shields.io/ansible/role/d/4809)](https://galaxy.ansible.com/buluma/puppet)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-puppet.svg)](https://github.com/buluma/ansible-role-puppet/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-puppet.svg)](https://github.com/buluma/ansible-role-puppet/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-puppet.svg)](https://github.com/buluma/ansible-role-puppet/pulls/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-puppet/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: yes

  # pre_tasks:
  #   - include: java-11.yml

  roles:
    - role: buluma.java
      when: ansible_os_family == 'Debian'
    - role: buluma.puppet
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-puppet/blob/master/defaults/main.yml):

```yaml
---
puppet_package: puppetserver

puppet_service: puppetserver
puppet_service_state: started
puppet_service_enabled: false
puppet_service_manage: false

puppet_bin_path: /opt/puppetlabs/bin

# Used only for Debian/Ubuntu.
puppet_apt_deb: "https://apt.puppetlabs.com/puppet6-release-{{ ansible_distribution_release }}.deb"

# Used only for RedHat/CentOS.
puppet_yum_rpm: "https://yum.puppet.com/puppet6-release-el-{{ ansible_distribution_major_version }}.noarch.rpm"
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-puppet/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.java](https://galaxy.ansible.com/buluma/java)|[![Build Status GitHub](https://github.com/buluma/ansible-role-java/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-java/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-java/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-java)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-puppet/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Debian](https://hub.docker.com/repository/docker/buluma/debian/general)|all|
|[EL](https://hub.docker.com/repository/docker/buluma/enterpriselinux/general)|8|
|[Ubuntu](https://hub.docker.com/repository/docker/buluma/ubuntu/general)|bionic, focal|
|[Kali](https://hub.docker.com/repository/docker/buluma/kali/general)|all|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-puppet/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-puppet/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-puppet/blob/master/LICENSE).

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)

Please consider [sponsoring me](https://github.com/sponsors/buluma).

### [Special Thanks](#special-thanks)

Template inspired by [Robert de Bock](https://github.com/robertdebock)
