# elastiflow

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&amp;logoColor=white)](https://github.com/rolehippie/elastiflow)
[![General Workflow](https://github.com/rolehippie/elastiflow/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/elastiflow/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/elastiflow/actions/workflows/readme.yml/badge.svg)](https://github.com/rolehippie/elastiflow/actions/workflows/readme.yml)
[![Galaxy Workflow](https://github.com/rolehippie/elastiflow/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/elastiflow/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/elastiflow)](https://github.com/rolehippie/elastiflow/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.elastiflow-blue)](https://galaxy.ansible.com/rolehippie/elastiflow)

Ansible role to install and configure Elastiflow netflow processing.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

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
elastiflow_version: 4.0.1
```

## Discovered Tags

**_elastiflow_**


## Dependencies

- [rolehippie.logstash](https://github.com/rolehippie/logstash)

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
