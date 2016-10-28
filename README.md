Stable
<a href="https://travis-ci.org/rvm/rvm/branches"><img src="https://travis-ci.org/rvm/rvm.svg?branch=stable" align="center"></a>
<a href="https://www.bountysource.com/teams/rvm?utm_source=RVM&utm_medium=shield&utm_campaign=raised"><img src="https://api.bountysource.com/badge/team?team_id=506&style=raised" align="center"></a>
&nbsp;&nbsp;&nbsp;&nbsp;
Master
<a href="https://travis-ci.org/rvm/rvm/branches"><img src="https://travis-ci.org/rvm/rvm.svg?branch=master" align="center"></a>

# What's RVM

RVM is the acronym of Ruby enVironment Manager. It manages Ruby application environments and enables switching between them.

Homepage and more info: https://rvm.io/

## Installation

### Ubuntu

RVM have dedicated Ubuntu package, so all you need is to run to install stable version of RVM:
 
`apt-get install rvm`

If you need a different (newer) version of RVM, check [Upgrading](#upgrading) section below.

### Any other operating system

Make sure you have following required packages installed:

* `curl`

And then run:

`\curl -sSL https://get.rvm.io | bash -s stable`

### Additional installation options

Additional installation options and details about the installation process are described here: https://rvm.io/rvm/install

## Upgrading

You can upgrade RVM any time by running:
 
`rvm get VERSION`

Where `VERSION` should be replaced by one of the following values:

* `stable`              - latest stable RVM (good for servers)
* `master`              - latest RVM (might not be stable)
* `branch /path/branch` - branched version of RVM (for testing new features or bug fixes)

Additional upgrading options are described here: https://rvm.io/rvm/upgrading

## Usage

`rvm COMMAND [INTERPRETER] OPTIONS`

### Commands

More detailed information about commands listed below can be read after executing `rvm help COMMAND` or browsing documentation on RVM homepage https://rvm.io/.

* `alias`                - lets you set shortcut strings for convenience with `rvm use` tasks
* `autolibs`             - controls settings for automatically installing dependencies
* `cleanup`              - lets you remove stale source folders / archives and other miscellaneous data associated with rvm
* `config-get`           - display values for `RbConfig::CONFIG` variables
* `cron`                 - manages setup for using ruby in cron
* `current`              - print the current ruby version and the name of any gemset being used
* `debug`                - show info plus additional information for common issues
* `disk-usage`           - tells you how much disk space rvm install is using
* `do`                   - runs an arbitrary command against specified and/or all rubies
  * `--summary`            - print out a summary of the commands run
  * `-S`                   - specify the script file to load and run
* `docs`                 - tools to make installing ri and rdoc documentation easier
* `export`               - temporarily set an environment variable in the current shell
* `fetch`                - performs an archive / src fetch only of the selected ruby
* `fix-permissions`      - repairs broken permissions (e.g. by sudo or chef)
* `gemdir`               - display the path to the current gem directory (`GEM_HOME`)
* `gemset`               - gemsets - https://rvm.io/gemsets/
* `get`                  - `{head,stable,branch}` upgrades rvm to latest head, stable or branched version
* `group`                - tools for managing groups in multiuser installations
* `implode`              - removes the rvm installation completely. This means everything in `$rvm_path` (`~/.rvm` || `/usr/local/rvm`). This does not touch your profiles. However, this means that you must manually clean up your profiles and remove the lines which source RVM
* `info`                 - show the environment information for current ruby
* `install`              - install one or many ruby versions. See also: https://rvm.io/rubies/installing/
  * `--32`                 - install 32-bit rubies
  * `--64`                 - install 64-bit rubies (default)
  * `--docs`               - generate ri after installation
  * `--skip-gemsets`       - skip the installation of default gemsets
  * `--quiet-curl`         - make `curl` silent when fetching data
  * `--reconfigure`        - force `./configure` on install even if `Makefile` already exists
  * `--force`              - remove old installation with sources and force install
  * `--disable-binary`     - install from source instead of using binaries
  * `--bin`                - path for binaries to be placed (default: `~/.rvm/bin/.`)
  * `--patch`              - with MRI Rubies you may specify additional patches to apply before install - multiple patches should be comma separated `--patch a.patch[%prefix],b.patch` - `prefix` is an optional argument, which will be bypassed to the `-p` argument of the `patch` command and should be separated from patch file name with the `%` symbol.
  * `--ree-options`        - options passed directly to ree's `./installer` on the command line
  * `-C` | `--configure`   - custom configure options - multiple options can be specified, separated with comma
  * `-l` | `--level`       - MRI ruby patch level
* `list`                 - show currently installed rubies, interactive output - https://rvm.io/rubies/list/
* `migrate`              - lets you migrate all gemsets from one ruby to another
* `mount`                - install rubies from external locations
* `notes`                - display notes with operating system specifics
* `osx-ssl-certs`        - helps update certificates for OpenSSL installed by rvm on OSX
* `patchset`             - tools related to managing ruby patchsets
* `pkg`                  - install a dependency package `{readline,iconv,zlib,openssl}` - https://rvm.io/packages/
* `reinstall`            - reinstall ruby and runs `gem pristine` on all gems. Make sure to read output. Use `all` for all rubies
* `reload`               - reload rvm source itself (useful after changing rvm source).
* `remove`               - uninstall one or many ruby versions and remove their sources
  * `--gems`               - also removes gems installed for the removed ruby version
  * `--archive`            - remove archives
* `repair`               - lets you repair parts of your environment e.g. wrappers, env files and similar (e.g. general maintenance)
* `requirements`         - installs additional OS specific dependencies/requirements for building various rubies (by default run by `install`)
* `reset`                - remove current and stored default & system settings
* `rubygems`             - switches the installed version of rubygems for the current ruby
* `rvmrc`                - tools related to managing `.rvmrc` trust and loading
* `snapshot`             - lets you backup / restore an rvm installation in a lightweight manner
* `tools`                - provides general information about the ruby environment, primarily useful when scripting rvm
* `unexport`             - undo changes made to the environment by `rvm export`
* `uninstall`            - uninstall one or many ruby versions, keeping their sources
  * `--gems`               - also removes gems installed for the removed ruby version
* `upgrade`              - lets you upgrade from one version of a ruby to another, including migrating your gemsets semi-automatically
* `usage`                - list available commands and their usage info (content of this README)
* `use`                  - setup current shell to use a specific ruby version
  * `--default`            - sets selected ruby as the default
  * `-l` | `--level`       - MRI ruby patch level
* `user`                 - tools for managing RVM mixed mode in multiuser installations
* `version`              - display rvm version (equal to `rvm -v`) 
* `wrapper`              - generates a set of wrapper executables for a given ruby with the specified ruby and gemset combination. Used under the hood for passenger support and the like

### Ruby Interpreters

* **`ruby`**     - MRI/YARV Ruby (The Gold Standard)
* `default`    - use the default ruby (or the system ruby if a default hasn't been set) - https://rvm.io/rubies/default/
* `ironruby`   - IronRuby, NOT supported yet. Looking for volunteers to help.
* `jruby`      - JRuby - Ruby interpreter on the Java Virtual Machine.
* `macruby`    - MacRuby, insanely fast, can make real apps (Mac OS X Only).
* `maglev`     - GemStone Ruby, awesome persistent ruby object store.
* `rbx`        - Rubinius
* `system`     - use the system ruby (eg. pre-rvm state)

Historical interpreters which you can still install with RVM, but are not anymore developed and supported by their authors:

* `ree`        - Ruby Enterprise Edition - MRI Ruby with several custom patches for performance, stability, and memory

### Additional options

* `--debug`           - toggle debug mode on for very verbose output
* `--latest`          - with gemset `--dump` skips version strings for latest gem
* `--trace`           - toggle trace mode on to see EVERYTHING rvm is doing
* `--nice`            - process niceness (increase the value on slow computers, default `0`)
* `--with-rubies`     - specifies a string for rvm to attempt to expand for set operations
* `-e`                - execute code from the command line
* `-v` | `--version`  - display rvm version loaded for current shell


## Contributing

Any and all contributions offered in any form, past present or future, to the
RVM project are understood to be in complete agreement and acceptance with the
Apache License v2.0.

## License

Copyright (c) 2009-2011 Wayne E. Seguin
Copyright (c) 2011-2016 Michal Papis

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
