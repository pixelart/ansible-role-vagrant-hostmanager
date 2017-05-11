# Ansible Role: Vagrant Host Manager

[![Build Status](https://travis-ci.org/pixelart/ansible-role-vagrant-hostmanager.svg?branch=master)](https://travis-ci.org/pixelart/ansible-role-vagrant-hostmanager)

Installs the [Vagrant Host Manager](https://github.com/devopsgroup-io/vagrant-hostmanager) plugin on Ubuntu.

## Requirements

  - `pixelart.vagrant` >=1.3.0

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    vagrant_hostmanager_version: ''
    
An optional version constraint of the plugin, or empty. Same functionality as the `version` key in `pixelart.vagrant`.

    vagrant_hostmanager_manage_sudoers: false

If the sudoers file should be managed for passwordless vagrant up/down when using the `vagrant-hostmanager` plugin. If true, a `/etc/sudoers.d/vagrant-hostmanager` will be created. This works only if `vagrant_manage_sudoers` in the `pixelart.vagrant` role is true.

Important defaults from the dependency `pixelart.vagrant`, which are used too:

    vagrant_plugin_users: []
    
Add a list of user account names for which the plugin should be installed.

    vagrant_plugins: []

The `vagrant-hostmanager` should not be listed here anymore.

    vagrant_manage_sudoers: false
    
Must be set to true if you want to use the `vagrant_hostmanager_manage_sudoers`.

    vagrant_plugins_keep_updated: false
    
Must be set to true, if you want the plugin to be updated.

## Dependencies

Need Vagrant with `pixelart.vagrant` installed before.

## Example Playbook

    - hosts: phpdevs
      vars_files:
        - vars/main.yml
      roles:
        - pixelart.vagrant-hostmanager
        
*Inside `vars/main.yml`*:

    vagrant_plugin_users: ['username']

After the playbook runs, `vagrant-hostmanager` will be accessible for the account `username`.

## Code of Conduct

Please note that this project is released with a [Contributor Code of Conduct](CODE_OF_CONDUCT.md). By participating in this project you agree to abide by its terms.

## License

MIT, see the [LICENSE](LICENSE) file.

## Author Information

This role was created in 2017 by [pixelart GmbH](https://www.pixelart.at/).
