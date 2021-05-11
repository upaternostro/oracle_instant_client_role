# Oracle Instant Client Ansible role
![Logo](https://raw.githubusercontent.com/idealista/oracle_instant_client_role/master/logo.gif)

[![Build Status](https://travis-ci.com/idealista/oracle_instant_client_role.png)](https://travis-ci.com/idealista/oracle_instant_client_role)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-idealista.oracle_instant_client_role-B62682.svg)](https://galaxy.ansible.com/idealista/oracle_instant_client_role)



This ansible role installs [Oracle Instant Client](https://www.oracle.com/database/technologies/instant-client.html) in a Debian environment. It has been tested for Debian buster and stretch.

- [Getting Started](#getting-started)
	- [Prerequisities](#prerequisities)
	- [Installing](#installing)
- [Usage](#usage)
- [Testing](#testing)
- [Built With](#built-with)
- [Versioning](#versioning)
- [Authors](#authors)
- [License](#license)
- [Contributing](#contributing)

## Getting Started
These instructions will get you a copy of the role for your Ansible playbook. Once launched, it will install Oracle Instant Client in a Debian system.

### Prerequisities

Ansible 2.9.21 version installed.

Molecule 3.x.x version installed.

For testing purposes, [Molecule](https://molecule.readthedocs.io/) with [Docker](https://www.docker.com/) as driver and  [Goss] (https://github.com/aelsabbahy/goss) as verifier.

### Installing

Create or add to your roles dependency file (e.g requirements.yml):

```
- src: idealista.oracle_instant_client_role
  version: 1.2.0
  name: oracle_instant_client
```

Install the role with ansible-galaxy command:

```
ansible-galaxy install -p roles -r requirements.yml -f
```

Use in a playbook:

```
---
- hosts: someserver
  roles:
    - role: oracle_instant_client_role
```

## Usage

Look to the [defaults](defaults/main.yml) properties file to see the possible configuration properties, it is very likely that you will not need to override any variables.

If you want to reinstall the oracle instant client when the role is lauched override the ```instant_client_force_reinstall ``` to ```true```.

If you want to change the installed release override ```instant_client_version``` and/or ```instant_client_release_system```. [Here](https://www.oracle.com/database/technologies/instant-client/downloads.html) are the available versions.


## Testing

### Install dependencies

```sh
$ pipenv sync
```

For more information read the [pipenv docs](ipenv-fork.readthedocs.io/en/latest/).

### Testing

```sh
$ pipenv run molecule test 
```

## Built With

![Ansible](https://img.shields.io/badge/ansible-2.9.21-green.svg)
![Molecule](https://img.shields.io/badge/molecule-3.0.4-green.svg)
![Goss](https://img.shields.io/badge/goss-0.3.16-green.svg)

## Versioning

For the versions available, see the [tags on this repository](https://github.com/idealista/oracle_instant_client_role/tags).

Additionaly you can see what change in each version in the [CHANGELOG.md](CHANGELOG.md) file.

## Authors

* **Idealista** - *Work with* - [idealista](https://github.com/idealista)

See also the list of [contributors](https://github.com/idealista/oracle_instant_client_role/contributors) who participated in this project.

## License

![Apache 2.0 License](https://img.shields.io/hexpm/l/plug.svg)

This project is licensed under the [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) license - see the [LICENSE](LICENSE) file for details.

## Contributing

Please read [CONTRIBUTING.md](.github/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.
