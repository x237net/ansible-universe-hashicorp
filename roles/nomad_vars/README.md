<!-- roles/nomad_vars/README.md
  -- ==========================
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

universe.hashicorp.nomad_vars
=============================

Purpose
-------

The `universe.hashicorp.nomad_vars` role defines a set of common variables for
[Hashicorp Nomad](https://www.nomadproject.io/), a workload orchestrator.

Dependencies
------------

This role depends on the following roles:

`universe.unix.dirs`
: To get installation directories of the system.

Variables
---------

The role accepts the following configuration variables:

### Optional

`nomad_vars_port_http` (Default: `4646`)
: The HTTP port to provide UI and API access to Hashicorp Nomad agents.

`nomad_vars_port_rpc` (Default: `4647`)
: The RPC protocol port used by Hashicorp Nomad agents.

`nomad_vars_port_serf` (Default: `4648`)
: The Gossip protocol port to manage Hashicorp Nomad server membership using
Serf.

`nomad_vars_system_username` (Default: `"root"`)
: A user name which will own the binary and installed directories.

`nomad_vars_system_groupname` (Default: `"{{ nomad_vars_system_username }}"`)
: A group name which will own the binary and installed directories.
