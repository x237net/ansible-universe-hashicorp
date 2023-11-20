<!-- roles/install/README.md
  -- =======================
  --
  -- Copying
  -- -------
  --
  -- Copyright (c) 2023 universe.hashicorp authors and contributors.
  --
  -- This file is part of the *universe.hashicorp* project.
  --
  -- *universe.hashicorp* is a free software project. You can redistribute it
  -- and/or modify it following the terms of the MIT License.
  --
  -- This software project is distributed *as is*, WITHOUT WARRANTY OF ANY KIND;
  -- including but not limited to the WARRANTIES OF MERCHANTABILITY, FITNESS FOR
  -- A PARTICULAR PURPOSE and NONINFRINGEMENT.
  --
  -- You should have received a copy of the MIT License along with
  -- *universe.hashicorp*. If not, see <http://opensource.org/licenses/MIT>.
  -->

universe.hashicorp.install
==========================

The `universe.hashicorp.install` role will fetch and install any package
provided by Hashicorp at [releases.hashicorp.com](
https://releases.hashicorp.com/).

This should work with some common packages but make sure that the process used
in this role is actually doing what you need.

Dependencies
------------

This role depends on the following roles:

`universe.unix.dirs`
: To get installation directories of the system.

`universe.unix.gpg_import`
: To import the `hashicorp` public key for verification of the installation
package.

`universe.unix.package_install`
: To install required packages on the system.

Variables
---------

The role exposes the following variables for its configuration:

### Required

`install_package_name`
: Name of the Hashicorp package to be downloaded and installed. The name should
match any package [released](https://releases.hashicorp.com/) by
Hashicorp.

### Optional

`install_force` (Default: `false`)
: When `true`, the package will be reinstalled even if the requested version is
running on the system.

`install_package_service_content` (Default: `null`)
: If the package is to be run as a systemd service, this variable contains the
content of a systemd service unit file.

`install_package_version` (Default: `"latest"`)
: The version of the package to be installed. When not provided, the role will
attempt to fetch the latest version available providing it is published on
[Hashicorp Checkpoint](https://checkpoint.hashicorp.com/).

`install_system_username` (Default: `"root"`)
: A user name which will own the binary and installed directories.

`install_system_groupname` (Default: `"{{ install_system_username }}"`)
: A group name which will own the binary and installed directories.
