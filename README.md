# Forked!

Fork from https://github.com/ElaoInfra/ansible-role-ohmyzsh

There were errors with ansible-galaxy while installing. 

I guess it's due to the fact that there are no releases or the main branch is not called master in the original repository.

Anyways...


# Ansible Role: OhMyZsh (see: [https://github.com/robbyrussell/oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh))

This role will assume the following configuration:
- Install ohmyzsh globally
- Setup a local zshrc file

## Requirements

- Ansible 1.7.2+

## Dependencies

None.

## Installation

Using ansible galaxy:

```bash
ansible-galaxy install elao.ohmyzsh
```
You can add this role as a dependency for other roles by adding the role to the meta/main.yml file of your own role:

```yaml
dependencies:
  - { role: elao.ohmyzsh }
```

## Role Handlers

None

## Role Variables

|Name|Default|Type|Description|
|----|----|-----------|-------|
`elao_ohmyzsh_users`|Array|Array|Collection of users with ohmyzsh custom configurations.
`user.name`|-|String|Name of the user (Need to match a unix system username).
`user.theme`|-|String|OhMyZsh theme see: [OhMyZsh themes](https://github.com/robbyrussell/oh-my-zsh/wiki/themes).
`user.plugins`|-|Array|Array of ohmyzsh plugins see: [OhMyZsh plugins](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins)

### Configuration example

```
---

elao_ohmyzsh_users:
  - name:    root
    theme:   pygmalion
    plugins: ['debian', 'common-aliases', 'history', 'history-substring-search']
  - name:    elao
    theme:   pygmalion
    plugins: ['debian', 'common-aliases', 'history', 'history-substring-search']
```

## Example playbook

    - hosts: servers
      roles:
         - { role: elao.ohmyzsh }

# Licence

MIT

# Author information

ELAO [**(http://www.elao.com/)**](http://www.elao.com)
