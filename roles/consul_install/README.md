<!-- roles/consul_install/README.md
  -- ==============================
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

universe.hashicorp.consul_install
=================================

The `universe.hashicorp.consul_install` role will fetch and install [Hashicorp
Consul](https://www.consul.io/), a service mesh solution providing a full
control plane with service discovery.

Dependencies
------------

This role depends on the following roles:

`universe.unix.dirs`
: To get installation directories of the system.

`universe.hashicorp.consul_install`
: To install required the Hashicorp provided package on the system.

Variables
---------

The role exposes the following variables for its configuration:

### Optional

`consul_install_dns_port` (Default: `0`)
: The DNS port on which Consul is meant to listen to. When set to `53`, the
standard port for DNS, the Consul service is given the `CAP_NET_BIND_SERVICE` in
order to run as a non-root user.

`consul_install_system_username` (Default: `"consul"`)
: A user name which will own the binary and installed directories.

`consul_install_system_groupname` (Default: `"{{ consul_install_system_username }}"`)
: A group name which will own the binary and installed directories.
