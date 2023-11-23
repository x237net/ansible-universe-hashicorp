<!-- roles/nomad_service/README.md
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

universe.hashicorp.nomad_service
================================

Purpose
-------

The `universe.hashicorp.nomad_service` role configures [Hashicorp Nomad](
https://www.nomadproject.io/), a workload orchestrator.

Variables
---------

The role exposes the following variables for its configuration:

### Required

`nomad_service_tls`
: Required when `nomad_use_tls` is set to `true`. A dictionary with the
following keys:

- `ca_file` (optional) — Path to a PEM-encoded certificate authority file.
- `cert_file` — Path to a PEM-encoded certificate file.
- `key_file` — Path to a PEM-encoded private key file.

### Optional

`nomad_service_bind_address` (Default:
`"{{ ansible_facts.default_ipv4.address }}"`)
: Specifies which address the Hashicorp Nomad agent should bind to for network
services.

`nomad_service_class` (Default: `""`)
: An arbitrary string used to logically group client nodes.

`nomad_service_is_client` (Default: `false`)
: Configures the Hashicorp Nomad agent to accept jobs as assigned by the
Hashicorp Nomad server.

`nomad_service_datacenter` (Default: `"dc1"`)
: Specifies the data center of the local agent.

`nomad_service_drivers` (Default: `[]`)
: A list of [task drivers](https://developer.hashicorp.com/nomad/docs/drivers)
supported by the Hashicorp Nomad client.

`nomad_service_http_port` (Default: `4646`)
: The HTTP port to provide UI and API access to Hashicorp Nomad agents.

`nomad_service_pool` (Default: `""`)
: Specifies the node pool in which the client is registered.

`nomad_service_region` (Default: `"global"`)
: Specifies the region the Hashicorp Nomad agent is a member of.

`nomad_service_rpc_port` (Default: `4647`)
: The RPC protocol port used by Hashicorp Nomad agents.

`nomad_service_serf_port` (Default: `4648`)
: The Gossip protocol port to manage Hashicorp Nomad server membership using
Serf.

`nomad_service_is_server` (Default: `false`)
: Configures the Hashicorp Nomad agent to operate in server mode to participate
in scheduling decisions.

`nomad_service_service_start` (Default: `true`)
: Should the Hashicorp Nomad service be started?

`nomad_service_use_tls` (Default: `false`)
: Enforces secure TLS for Hashicorp Nomad's HTTP and RPC communication.
