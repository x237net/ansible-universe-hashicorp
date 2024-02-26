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

Configuration
-------------

Use the `universe.hashicorp.consul_vars` role to configure the different aspects
of this role.

Dependencies
------------

This role depends on the following roles:

`universe.unix.dirs`
: To get installation directories of the system.

`universe.hashicorp.install`
: To install required the Hashicorp provided package on the system.

`universe.hashicorp.consul_vars`
: For common Hashicorp Consul configuration variables.
