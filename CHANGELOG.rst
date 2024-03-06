.. CONTRIBUTORS.rst
.. ================
..
.. Copying
.. -------
..
.. Copyright (c) 2022 universe.hashicorp authors and contributors.
..
.. This file is part of the *universe.hashicorp* project.
..
.. *universe.hashicorp* is a free software project. You can redistribute it
.. and/or modify it following the terms of the MIT License.
..
.. This software project is distributed *as is*, WITHOUT WARRANTY OF ANY KIND;
.. including but not limited to the WARRANTIES OF MERCHANTABILITY, FITNESS FOR A
.. PARTICULAR PURPOSE and NONINFRINGEMENT.
..
.. You should have received a copy of the MIT License along with
.. *universe.hashicorp*. If not, see <http://opensource.org/licenses/MIT>.

================================
universe.hashicorp Release Notes
================================

.. contents:: Topics


v0.2.0
======

Release Summary
---------------

Fixup of a few issues.

Major Changes
-------------

- consul_install - systemd service has been changed to run Hashicorp Consul with
  protected ``/home`` and read-only system folders.
- nomad_service - Removed dependency on ``consul_install``. Users must now
  manually install Hashicorp Consul and set the variable
  ``nomad_service_use_consul`` to ``true``.

Minor Changes
-------------

- consul_vars - Added the ``consul_vars_statedir`` variable to configure runtime
  files location for Hashicorp Consul.
- install - Now accept ``install_bindir``, ``install_confdir``, and
  ``install_statedir`` variables to specify respectively installation
  directories for binaries, configuration and runtime files of the Hashicorp
  package.
- nomad_vars - Added the ``nomad_vars_statedir`` variable to configure runtime
  files location for Hashicorp Nomad.

v0.1.0
======

Release Summary
---------------

First release of the ``universe.hashicorp`` collection. Everything must be
considered early stage and not yet ready for production.
