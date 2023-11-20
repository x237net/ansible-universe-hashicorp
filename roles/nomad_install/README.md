<!-- roles/nomad_install/README.md
  -- =============================
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

universe.hashicorp.nomad_install
================================

The `universe.hashicorp.nomad_install` role installs [Hashicorp Nomad](
https://www.nomadproject.io/), a flexible scheduler and orchestrator to
deploy and manage containers and non-containerized applications.

Dependencies
------------

This role depends on the following roles:

`universe.unix.dirs`
: To get installation directories of the system.

`universe.hashicorp.consul_install`
: To install Consul along with Nomad.

`universe.hashicorp.install`
: To install Nomad on the system.
