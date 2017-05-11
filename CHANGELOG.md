# Change Log
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/) 
and this project adheres to [Semantic Versioning](http://semver.org/).

## [Unreleased]
### Added
- Keep vagrant-hostmanager updated if configured

### Upgrade needed
If you have ever configured `vagrant_hostmanager_version: 'latest'` in your own vars, you should to change it to be empty or better remove it and deal with the default and set. `latest` will still work, but it's discouraged.

To gain the behaviour the setting with `latest` promised before you need to set `vagrant_plugins_keep_updated` to true.

## [1.0.0] - 2017-02-09
### Added
- Create role to provision vagrant-hostmanager plugin
- Add functionality to manage a sudoers entry for the plugin
- Test the role on Ubuntu 16.04

[Unreleased]: https://github.com/pixelart/ansible-role-vagrant-hostmanager/compare/1.0.0...HEAD
[1.0.0]: https://github.com/pixelart/ansible-role-vagrant-hostmanager/compare/90ddaa5...1.0.0
