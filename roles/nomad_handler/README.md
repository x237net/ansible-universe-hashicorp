<!-- roles/nomad_handler/README.md
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

universe.hashicorp.nomad_handler
================================

Purpose
-------

The `universe.hashicorp.nomad_handler` provides common handlers for [Hashicorp Nomad](
https://www.nomadproject.io/). This role is meant to be used as a dependency for other roles when they need a Nomad handler.

Dependencies
------------

This role depends on the following roles:

`universe.hashicorp.nomad_vars`
: For common Hashicorp Nomad configuration variables.

Handlers
--------

`universe.hashicorp.nomad_handler:client_config_updated`
: Notify that a Nomad client configuration file has been updated.

`universe.hashicorp.nomad_handler:client_service_reload`
: Ask for the Nomad client service to reload its configuration files.

`universe.hashicorp.nomad_handler:client_service_start`
: Start the Nomad client service.

`universe.hashicorp.nomad_handler:server_config_updated`
: Notify that a Nomad server configuration file has been updated.

`universe.hashicorp.nomad_handler:server_service_reload`
: Ask for the Nomad server service to reload its configuration files.

`universe.hashicorp.nomad_handler:server_service_start`
: Start the Nomad server service.
