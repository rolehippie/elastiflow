# elastiflow

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/elastiflow) [![Build Status](https://img.shields.io/drone/build/rolehippie/elastiflow/master?logo=drone)](https://cloud.drone.io/rolehippie/elastiflow) [![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/elastiflow)](https://github.com/rolehippie/elastiflow/blob/master/LICENSE) 

Ansible role to install and configure Elastiflow netflow processing. 

## Sponsor 

[![Proact Deutschland GmbH](https://proact.eu/wp-content/uploads/2020/03/proact-logo.png)](https://proact.eu) 

Building and improving this Ansible role have been sponsored by my employer **Proact Deutschland GmbH**.

## Table of content

* [Default Variables](#default-variables)
  * [elastiflow_elasticsearch_hosts](#elastiflow_elasticsearch_hosts)
  * [elastiflow_elasticsearch_password](#elastiflow_elasticsearch_password)
  * [elastiflow_elasticsearch_username](#elastiflow_elasticsearch_username)
  * [elastiflow_repository](#elastiflow_repository)
  * [elastiflow_version](#elastiflow_version)
  * [logstash_repository](#logstash_repository)
* [Dependencies](#dependencies)
* [License](#license)
* [Author](#author)

---

## Default Variables

### elastiflow_elasticsearch_hosts

#### Default value

```YAML
elastiflow_elasticsearch_hosts: []
```

### elastiflow_elasticsearch_password

#### Default value

```YAML
elastiflow_elasticsearch_password:
```

### elastiflow_elasticsearch_username

#### Default value

```YAML
elastiflow_elasticsearch_username:
```

### elastiflow_repository

Repository to clone Elastiflow from

#### Default value

```YAML
elastiflow_repository: https://github.com/robcowart/elastiflow.git
```

### elastiflow_version

#### Default value

```YAML
elastiflow_version: v3.5.3
```

### logstash_repository

List of elasticsearch hosts to write into

## Dependencies

* None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
