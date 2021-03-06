# djbdns Cookbook CHANGELOG

This file is used to list changes made in each version of the djbdns cookbook.

## v2.0.0 (2016-05-20)

### BREAKING CHANGE:

This version removes support for bluepill and daemontools init systems and Arch Linux. If you rely on that support you'll want to pin to the 1.2.0 release

This version now manages all djbdns env files to be compatible with the newest runit release. If you manage these files outside of the djbdns recipe you'll need to use the new attributes

## v1.2.0:

- Removed newlines in configs to prevent restarts
- Removed inclusion of ucspi-tcp recipe for source installs
- Convert hashes to Ruby 1.9+ format
- Bump Runit dependency to 1.6.0 from 1.5.0
- Updated Test Kitchen config with the latest platforms and a suite for source install
- Added Travis CI config
- Added a simple contributing doc to replace the Chef Software Inc version
- Updated the development gem requirements and break gems into groups in the gemfile
- Added a cookbook version badge in the readme
- Added a chefignore file to limit what files are uploaded to the chef server
- Added additional platforms to the metadata
- Add source_url and issues_url to the metadata
- Make modes strings to preserve the leading 0s
- Resolve rubocop warnings
- Added additional unit tests

## v1.1.0:

- Update dependency for current runit cookbook, #7
- Debian is a source based platform, #9 (see issue for background)
- Add `package_name` attribute to allow for installing [dbndns](http://en.wikipedia.org/wiki/Dbndns), #16, related to #9
- Use runit as default service type instead of bluepill, #10
- Drop explicit support for old unsupported Ubuntu versions, #11
- Manage runit's sv dir for "reasons," #12
- Remove attributes from metadata, as they're not used for anything anywhere anyway

## v1.0.2:

- [COOK-2262] - pin runit dependency

## v1.0.0:

- [COOK-1739] - use node attributes with hash notation instead of just the attribute name (ipaddress, domain) in djbdns attributes file
- [COOK-1742] - fix foodcritic warnings, use platform_family where apropriate

## v0.99.4:

- [COOK-1259] - Support local (10.x, 172.x, 192.168.x) reverse lookups in cache

## v0.99.2:

- [COOK-1042] - Corrected a syntax error in axfr.
- [COOK-740] - use correct directory for tinydns root data

## Previous versions:

The various recipes now support multiple service types. This is controlled with the `node[:djbdns][:service_type]` attribute, which is set by platform in the default recipe.

ArchLinux support has been added, as well as naively attempting other platforms by source-compiled installation with bluepill for service management.
