<!-- roles/consul_service/README.md
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

universe.hashicorp.consul_service
=================================

Purpose
-------

The `universe.hashicorp.consul_service` configures [Hashicorp
Consul](https://www.consul.io/), a service mesh solution providing a full
control plane with service discovery.

Dependencies
------------

This role depends on the following roles:

`universe.hashicorp.consul_vars`
: For common Hashicorp Consul configuration variables.

Variables
---------

The role exposes the following variables for its configuration:

### Required

`consul_service_tls`
: Required when `consul_service_use_tls` is set to `true`. A dictionary with the
following keys:

- `ca_file` (optional) — Path to a PEM-encoded certificate authority file. The
  certificate authority is used to check the authenticity of client and server
  connections.
- `ca_path` (optional) — Path to a directory of PEM-encoded certificate
  authority files. These certificate authorities are used to check the
  authenticity of client and server connections.
- `cert_file` — Path to a PEM-encoded certificate file. The certificate is
  provided to clients or servers to verify the agent's authenticity.
- `key_file` — Path to a PEM-encoded private key file. The key is used with the
  certificate to verify the agent's authenticity.

### Optional

`consul_service_addresses` (Default: `{}`)
: A dictionary listing the addresses Consul should bind to for each service.
When not set, all services bind to `consul_service_bind_address`. The following
keys are valid:

- `dns` — The DNS server.
- `http` — The HTTP API.
- `https` — The HTTPS API.
- `grpc` — The gRPC API.
- `grpc_tls` — The gRPC API with TLS.

`consul_service_bind_address` (Default: `"127.0.0.1"`)
: The IP address the Consul server will bind to for client communication.

`consul_service_cluster_bind_address` (Default:
`"{{ ansible_facts.default_ipv4.address }}"`)
: The IP address the Consul server will bind to for cluster communication.

`consul_service_datacenter` (Default: `"dc1"`)
: The datacenter in which the Consul cluster is located.

`consul_service_dns_port` (Default: `8600`)
: The port to be exposed on the system for DNS queries.

`consul_service_http_port` (Default: `8500`)
: The port to be exposed on the system for the HTTP ui.

`consul_service_https_port` (Default: `8501`)
: The port to be exposed on the system for the HTTPS ui.

`consul_service_primary_datacenter` (Default:
`"{{ consul_service_datacenter }}"`)
: The authoritative datacenter for Consul.

`consul_service_serf_lan_port` (Default: `8301`)
: This is used to handle gossip in the LAN.

`consul_service_serf_wan_port` (Default: `8302`)
: This is used by servers to gossip over the WAN, to other servers.

`consul_service_servers` (Default: `[]`)
: Addresses of other Consul agents to join upon starting up.

`consul_service_server_port` (Default: `8300`)
: This is used by the server to handle incoming requests from other servers.

`consul_service_start` (Default: `true`)
: Should the Hashicorp Consul service be started?

`consul_service_ui_enabled` (Default: `true`)
: Whether to enable the Web interface for Consul.

`consul_service_use_tls` (Default: `false`)
: Configure Consul to use TLS encrypted communication. When set to `true`, the
`consul_service_tls` variable is required.
