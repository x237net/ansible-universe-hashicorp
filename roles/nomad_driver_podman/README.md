<!-- roles/nomad_driver_podman/README.md
  -- ===================================
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

universe.hashicorp.nomad_driver_podman
======================================

Purpose
-------

The `universe.hashicorp.nomad_driver_podman` role installs and configures the
[Podman](https://developer.hashicorp.com/nomad/plugins/drivers/podman) driver
for Hashicorp Nomad.

Dependencies
------------

This role depends on the following roles:

`universe.hashicorp.install`
: To install the Podman driver.

`universe.hashicorp.nomad_vars`
: For common Hashicorp Nomad configuration variables.

Variables
---------

The role exposes the following variables for its configuration:

`nomad_service_use_tls` (Default: `false`)
: Enforces secure TLS for Hashicorp Nomad's HTTP and RPC communication.

nomad_driver_podman_version: "0.5.2"
nomad_driver_podman_install_force: false

nomad_driver_podman_disable_log_collection: false
nomad_driver_podman_gc_container: true
nomad_driver_podman_socket_path: null
nomad_driver_podman_client_http_timeout: "60s"
nomad_driver_podman_volumes_enabled: true
nomad_driver_podman_volumes_selinux_label: "z"
