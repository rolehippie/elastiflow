# elastiflow

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/elastiflow) [![Testing Build](https://github.com/rolehippie/elastiflow/workflows/testing/badge.svg)](https://github.com/rolehippie/elastiflow/actions?query=workflow%3Atesting) [![Readme Build](https://github.com/rolehippie/elastiflow/workflows/readme/badge.svg)](https://github.com/rolehippie/elastiflow/actions?query=workflow%3Areadme) [![Galaxy Build](https://github.com/rolehippie/elastiflow/workflows/galaxy/badge.svg)](https://github.com/rolehippie/elastiflow/actions?query=workflow%3Agalaxy) [![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/elastiflow)](https://github.com/rolehippie/elastiflow/blob/master/LICENSE)

Ansible role to install and configure Elastiflow netflow processing.

## Sponsor

[![Proact Deutschland GmbH](https://proact.eu/wp-content/uploads/2020/03/proact-logo.png)](https://proact.eu)

Building and improving this Ansible role have been sponsored by my employer **Proact Deutschland GmbH**.

## Table of content

- [Default Variables](#default-variables)
  - [elastiflow_configs](#elastiflow_configs)
  - [elastiflow_download](#elastiflow_download)
  - [elastiflow_elasticsearch_hosts](#elastiflow_elasticsearch_hosts)
  - [elastiflow_elasticsearch_password](#elastiflow_elasticsearch_password)
  - [elastiflow_elasticsearch_username](#elastiflow_elasticsearch_username)
  - [elastiflow_version](#elastiflow_version)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Default Variables

### elastiflow_configs

List of configs to enable or disable

#### Default value

```YAML
elastiflow_configs:
  - name: 30_output_10_single
    state: "{{ 'enable' if elastiflow_elasticsearch_hosts | length < 2 else 'disable'\
      \ }}"
  - name: 30_output_20_multi
    state: "{{ 'enable' if elastiflow_elasticsearch_hosts | length > 1 else 'disable'\
      \ }}"
```

### elastiflow_download

URL to fetch the elastiflow source from

#### Default value

```YAML
elastiflow_download: https://github.com/robcowart/elastiflow/archive/refs/tags/v{{
  elastiflow_version }}.tar.gz
```

### elastiflow_elasticsearch_hosts

List of elasticsearch hosts to write into

#### Default value

```YAML
elastiflow_elasticsearch_hosts: []
```

### elastiflow_elasticsearch_password

Optional password for elastisearch authentication

#### Default value

```YAML
elastiflow_elasticsearch_password:
```

### elastiflow_elasticsearch_username

Optional username for elasticsearch authentication

#### Default value

```YAML
elastiflow_elasticsearch_username:
```

### elastiflow_version

Version of the archive to download

#### Default value

```YAML
elastiflow_version: 3.5.3
```

## Discovered Tags

**_elastiflow_**


## Dependencies

- None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
