<!-- roles/consul_vars/README.md
  -- ===========================
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

universe.hashicorp.consul_vars
==============================

Purpose
-------

The `universe.hashicorp.consul_vars` defines a set of common variables for
[Hashicorp Consul](https://www.consul.io/), a service mesh solution providing a
full control plane with service discovery.

Dependencies
------------

This role depends on the following roles:

`universe.unix.dirs`
: To get installation directories of the system.

Variables
---------

The role accepts the following configuration variables:

`consul_vars_dns_port` (Default: `8600`)
: The port to be exposed on the system for DNS queries.

`consul_vars_http_port` (Default: `8500`)
: The port to be exposed on the system for the HTTP ui.

`consul_vars_https_port` (Default: `8501`)
: The port to be exposed on the system for the HTTPS ui.

`consul_vars_serf_lan_port` (Default: `8301`)
: This is used to handle gossip in the LAN.

`consul_vars_serf_wan_port` (Default: `8302`)
: This is used by servers to gossip over the WAN, to other servers.

`consul_vars_server_port` (Default: `8300`)
: This is used by the server to handle incoming requests from other servers.

`consul_vars_system_username` (Default: `"consul"`)
: A user name which will own the binary and installed directories.

`consul_vars_system_groupname` (Default: `"{{ consul_vars_system_username }}"`)
: A group name which will own the binary and installed directories.
