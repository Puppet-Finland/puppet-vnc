# Reference

<!-- DO NOT EDIT: This document was generated by Puppet Strings -->

## Table of Contents

### Classes

#### Public Classes

* [`vnc::client::gui`](#vncclientgui): Install the VNC GUI clients
* [`vnc::server`](#vncserver): Install and configure the tigervnc server

#### Private Classes

* `vnc::server::config`: Configure the VNC services
* `vnc::server::install`: Install the vnc server pacakges
* `vnc::server::service`: Ensure the VNC Server services are right

## Classes

### <a name="vncclientgui"></a>`vnc::client::gui`

Install the VNC GUI clients

#### Parameters

The following parameters are available in the `vnc::client::gui` class:

* [`manage_packages`](#manage_packages)
* [`packages`](#packages)
* [`packages_ensure`](#packages_ensure)

##### <a name="manage_packages"></a>`manage_packages`

Data type: `Boolean`

Should this class manage the packages

##### <a name="packages"></a>`packages`

Data type: `Array`

List of packages to install

##### <a name="packages_ensure"></a>`packages_ensure`

Data type: `String`

Ensure state of the vnc client packages

### <a name="vncserver"></a>`vnc::server`

This class will install and configure the tigervnc
server, setup defaults, and manage the services.

 The default state is running/enabled, not user managed

#### Parameters

The following parameters are available in the `vnc::server` class:

* [`manage_packages`](#manage_packages)
* [`packages`](#packages)
* [`packages_ensure`](#packages_ensure)
* [`manage_config`](#manage_config)
* [`config_defaults_file`](#config_defaults_file)
* [`config_defaults`](#config_defaults)
* [`config_mandatory_file`](#config_mandatory_file)
* [`config_mandatory`](#config_mandatory)
* [`vncserver_users_file`](#vncserver_users_file)
* [`polkit_file`](#polkit_file)
* [`manage_services`](#manage_services)
* [`systemd_template_startswith`](#systemd_template_startswith)
* [`systemd_template_endswith`](#systemd_template_endswith)
* [`vnc_servers`](#vnc_servers)

##### <a name="manage_packages"></a>`manage_packages`

Data type: `Boolean`

Should this class manage the packages

##### <a name="packages"></a>`packages`

Data type: `Array`

List of packages to install

##### <a name="packages_ensure"></a>`packages_ensure`

Data type: `String`

Ensure state of the vnc server packages

##### <a name="manage_config"></a>`manage_config`

Data type: `Boolean`

Should this class manage the config

##### <a name="config_defaults_file"></a>`config_defaults_file`

Data type: `Stdlib::Absolutepath`

Your /etc/tigervnc/vncserver-config-defaults

##### <a name="config_defaults"></a>`config_defaults`

Data type: `Hash[String, Variant[String, Undef]]`

Settings to put in /etc/tigervnc/vncserver-config-defaults

##### <a name="config_mandatory_file"></a>`config_mandatory_file`

Data type: `Stdlib::Absolutepath`

Your /etc/tigervnc/vncserver-config-mandatory

##### <a name="config_mandatory"></a>`config_mandatory`

Data type: `Hash[String, Variant[String, Undef]]`

Settings to put in /etc/tigervnc/vncserver-config-mandatory

##### <a name="vncserver_users_file"></a>`vncserver_users_file`

Data type: `Stdlib::Absolutepath`

Your /etc/tigervnc/vncserver.users

##### <a name="polkit_file"></a>`polkit_file`

Data type: `Stdlib::Absolutepath`

Your /etc/polkit-1/rules.d/25-puppet-vncserver.rules

##### <a name="manage_services"></a>`manage_services`

Data type: `Boolean`

Should this class manage the vncserver services

##### <a name="systemd_template_startswith"></a>`systemd_template_startswith`

Data type: `String`

What does the vnc template service start with, including the '@'

##### <a name="systemd_template_endswith"></a>`systemd_template_endswith`

Data type: `String`

What does the vnc template service end with (not including the '.')

##### <a name="vnc_servers"></a>`vnc_servers`

Data type: `Hash[String, Hash[Enum['displaynumber', 'user_can_manage', 'comment', 'ensure', 'enable'], Variant[String, Integer, Boolean]]]`

A hash of VNC servers to setup  Format:
userA:
  comment: Sometimes you've gotta write it down
  displaynumber: 1
  ensure: running
  enable: true
  user_can_manage: true
userB:
  displaynumber: 2
  ensure: stopped
  enable: false
  user_can_manage: false
