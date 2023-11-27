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

universe.hashicorp.nomad_job
============================

Purpose
-------

The `universe.hashicorp.nomad_job` role pushes a jobs to a [Hashicorp Nomad](
https://www.nomadproject.io/) instance.

Variables
---------

The role exposes the following variables for its configuration:

### Required

`nomad_job_content`
: The content of the job to be pushed to Hashicorp Nomad.

### Optional

`nomad_job_host` (Default: `"localhost"`)
: The hostname of the Hashicorp Nomad instance.

`nomad_job_format` (Default: `"hcl"`)
: The format used to define the Hashicorp Nomad job. Must be one of `hcl` or
`json`.

`nomad_job_start` (Default: `true`)
: Should the provided job be forced to start after its submission to the
Hashicorp Nomad instance.

`nomad_job_timeout` (Default: `15`)
: The maximum amount of time in seconds to wait for a reply from Hashicorp
Nomad.

`nomad_job_use_tls` (Default: `true`)
: Whether to use secure TLS communication when sending the job to the Hashicorp
Nomad instance.
