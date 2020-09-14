<div align="center">
    <img src="./%40doc/figures/binbash-logo.png" 
    alt="binbash" width="250"/>
</div>
<div align="right">
  <img src="./%40doc/figures/binbash-leverage-ansible-logo.png"
  alt="leverage" width="130"/>
</div>

# Ansible Role: binbash_inc.ansible_role_common

**Ansible Role to install your Server pre-requisites packages including python pip packages.**

## Requirements

None.

### Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

This vars should be modified for your current use case. 

You can set your specific server name here, eg: infra-vpn-server, infra-ci-server, etc.
```
server_hostname: "infra-server"
```

These `server_pgk_list` variables expect valid debian based packages and python pip packages (optionally w/ versions)
```
server_pkg_list: [python3-pip,unzip,vim,zip]
server_pkg_list_pip: [awscli,boto,boto3,pyOpenSSL]
server_pkg_list_pip_ver: [[ansible,2.8.7],[docker,4.1.0]]
```

The `server_pip3` vars here confirm python pip binary upgrade passing an specific version to it.
```
server_pip3_upgrade: false
server_pip3_version: 19.3.1
```

## Dependencies

None.

### Example Playbook

With server hostname and installation of OS packages + python pip packages
```
  roles:
    - role: binbash_inc.ansible_role_common
      server_hostname: "infra-server"
      server_pkg_list: [build-essential, python3-pip, python3-setuptools, software-properties-common, unzip, vim, zip]
      server_pkg_list_pip: [awscli, boto, boto3, pyOpenSSL]
      server_pkg_list_pip_ver: [[ansible, 2.8.7],[docker, 4.1.0]]
      server_pip3_upgrade: true
      server_pip3_version: 19.3.1
```

## License

MIT / BSD

# Release Management
### CircleCi PR auto-release job

<div align="left">
  <img src="./%40doc/figures/circleci-logo.png" alt="circleci" width="130"/>
</div>

- [**pipeline-job**](https://app.circleci.com/pipelines/github/binbashar/ansible-role-common) (**NOTE:** Will only run after merged PR)
- [**releases**](https://github.com/binbashar/ansible-role-common/releases) 
- [**changelog**](https://github.com/binbashar/ansible-role-common/blob/master/CHANGELOG.md) 
