# snowagent

Installs and configures the snowagent agent for the software asset management
(SAM) tool of UniBE.

## Requirements

No prerequisites necessary at the moment.


## Role Variables

Available variables are listed below, along with default values (see also
[defaults/main.yml](defaults/main.yml)):

For most use cases you should only change the `snowagent_sitename` (if not ID)
and adjust the `snowagent_excludes`, i.e. mounted NAS storage or other paths that
should get searched by the snowagent.

### snowagent_agent_state

    snowagent_agent_state: "present"

If set to "present", the Snow inventory agent is installed, while setting this
to "absent" will completely remove it from the system. Defaults to "present".

### snowagent_endpoint

    snowagent_endpoint: 'https://uni-sam-gw1.campus.unibe.ch'

The endpoint for the snowagent. This is the URL where the snowagent sending its
report to.

### snowagent_sitename

    snowagent_sitename: 'unibe-zb-id'

The name of the site that reports of the node should belong to. Defaults to the
correct value for the IT Service Office. Ask the SAM officials for the site name
for your organisation unit if your system does not belong to ID.

### snowagent_baseurl

    snowagent_baseurl: 'https://tools.id.unibe.ch/snowagent/'

Base URL where the snowagent packages are stored. Defaults to the base URL of
the IT Office of UniBE. If in doubt, use the default.

### snowagent_download_rpm

    snowagent_download_rpm: '{{ snowagent_baseurl }}unibe_snowagent-{{ snowagent_version }}.x86_64.rpm'

Download URL of the RPM package. Defaults to a computed value of the current
defaults of the IT Office of UniBE. If in doubt, use the default.

### snowagent_download_deb

    snowagent_download_deb: '{{ snowagent_baseurl }}unibe_snowagent-{{ snowagent_version }}_amd64.deb'

Download URL of the Debian package. Defaults to a computed value of the current
defaults of the IT Office of UniBE. If in doubt, use the default.

### snowagent_version

    snowagent_version: '7.0.1'

The version to be installed. The default reflect the version approved and
requested by the IT Office of UniBE.

### snowagent_loglevel

    snowagent_loglevel: 'warning'

The log level of the application. Possible values are error, warning, info, trace, verbose; defaults to warning.

### snowagent_excludes:

    snowagent_excludes:
      - '/home/*'
      - '/var/*'
      - '/storage/*'

By default, these three paths are excluded from the search. Depending on the use
case other paths should be removed, i.e. a NAS share mounted in the
filesystem.

## Dependencies

This role has no dependencies to other roles.

## Example Playbook

Reference this role in your playbook:
```yaml
  - name: Example playbook
    hosts: all
    become: true

    roles:
      - role: unibeid.snowagent
```
## Compatibility

This role has been written for and tested on and is therefore compatible with:

* Rocky Linux 8, Rocky Linux 9
* Ubuntu 20.04, Ubuntu 22.04, Ubuntu 24.04

## License

MIT

## Author Information

The role was created in 2023 by the IT-Services Office of the University of Bern
