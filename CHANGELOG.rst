.. CHANGELOG.rst
.. =============
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


v0.3.0
======

Release Summary
---------------

Refactor Nomad roles to allow for Nomad drivers installation and to run
Hashicorp Nomad clients as non-privileged users.

Major Changes
-------------

- nomad_handler - Move Nomad handlers to a dedicated role so that all
  other roles can benefit from them.
- nomad_install - The Nomad service is now divided between client and
  server. The ``nomad.service`` unit starts a Nomad server while the
  ``nomad-client.service`` unit starts a Nomad client.

Minor Changes
-------------

- install - The role can now only proceed with the binary installation
  without setting up the environment. This can also be used to install
  application plugins.
- nomad_driver_podman - Add a role to install and configure the
  `Podman <https://developer.hashicorp.com/nomad/plugins/drivers/podman>`_
  driver for Hashicorp Nomad.
- nomad_install - Allow the Nomad client service to run as a non-root
  user.
- nomad_service - Add the configuration variable
  `nomad_service_is_user_client` to configure a Nomad client running as
  a non-root user.
- nomad_vars - Add the configuration variable `nomad_vars_confdir` to
  specify where Nomad is to find its configuration files.
- nomad_vars - The `nomad_vars_pluginsdir` variable can be used to
  configure the directory where Hashicorp Nomad will look for its
  plugins.

v0.2.1
======

v0.2.0
======

Release Summary
---------------

Fixup of a few issues.

Major Changes
-------------

- consul_install - systemd service has been changed to run Hashicorp
  Consul with protected ``/home`` and read-only system folders.
- nomad_service - Removed dependency on ``consul_install``. Users must
  now manually install Hashicorp Consul and set the variable
  ``nomad_service_use_consul`` to ``true``.

Minor Changes
-------------

- consul_vars - Added the ``consul_vars_statedir`` variable to
  configure runtime files location for Hashicorp Consul.
- install - Now accept ``install_bindir``, ``install_confdir``, and
  ``install_statedir`` variables to specify respectively installation
  directories for binaries, configuration and runtime files of the
  Hashicorp package.
- nomad_vars - Added the ``nomad_vars_statedir`` variable to
  configure runtime files location for Hashicorp Nomad.

v0.1.0
======

Release Summary
---------------

First release of the ``universe.hashicorp`` collection. Everything
must be considered early stage and not yet ready for production.
