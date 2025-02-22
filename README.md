# Openstef-reference

Reference implementation of the [OpenSTEF](https://github.com/OpenSTEF) stack. It includes all key functionality, e.g. the forecast engine, data storage and -models, the expert user dashboard!

## Table of contents 
- [Installation](#installation)
- [Usage](#usage)
- [Tips and Tricks](#tips-and-tricks)
- [License](#license)
- [Licenses third-party libraries](#licenses-third-party-libraries)
- [Contributing](#contributing)
- [Contact](#contact)


# Installation

## Prerequisites

Both Docker and Docker compose have to be installed. It is recommended to follow the instruction of the corresponding page:

### Install Docker

Follow the instruction on the Get Docker page: https://docs.docker.com/get-docker/

### Install Docker Compose

Follow the instruction on the Install Docker Compose page: https://docs.docker.com/compose/install/

# Usage

To start using the **OpenSTEF** reference stack use Docker Compose to bring up the whole stack:

```shell
$ sudo docker-compose up
```

Note: if you're running docker on a windows machine, issues might be caused by windows line endings.
All line endings should be Unix!

## Grafana

Open on http://localhost:3000
Log in using username `admin` and password `admin`

Set the mysql pasword (`root`) from withing the dashboard. Do this via Configuration > DataSources > tst_icarus (MySQL) > password.

Set the influx token pasword (`mytoken`) from withing the dashboard. Do this via Configuration > DataSources >  InfluxDB-V2 > token.

To view the dash board navigate to the dashboard: Dashboards > Station forecasts.

![screenshot](https://user-images.githubusercontent.com/60883372/146760483-29af3ac7-62af-4f13-98c7-982a79c517d1.jpg)
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fjoyshmitz%2Fopenstef-reference.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2Fjoyshmitz%2Fopenstef-reference?ref=badge_shield)
Screenshot of the operational dashboard showing the key functionality of OpenSTEF. 
Dashboard documentation can be found [here](https://github.com/OpenSTEF/.github/blob/main/profile/README.md).

## PhpMyAdmin

Open on http://localhost:8080
Log in using username `root` and password `root`

## Influx UI

Open on http://localhost:8086
Log in using username `myusername` and password `passwordpasswordpassword`

## Nginx

Open on http://localhost:8090

## Mlflow

Open on http://localhost:8099

## Running pipelines

In the root of the project run:

`pip install -r requirements.txt`

Run a training or forecast pipeline by running the corresponding python files in `openstef_example_tasks` from the root of this repository.

# Tips and tricks

## Enter running container

To enter the InfluxDB container run:

```shell
$ sudo docker exec -it openstef-influxdb /bin/bash
```

```shell
$ sudo docker exec -it openstef-nginx /bin/bash
```

## Clear the volumes

Docker will try using previous volumes on runs. But sometimes you want to start fresh. Docker-compose offers the `--renew-anon-volumes` option for this purpose:

```
$ docker-compose up --renew-anon-volumes
```

# License
This project is licensed under the Mozilla Public License, version 2.0 - see LICENSE for details.


[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fjoyshmitz%2Fopenstef-reference.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2Fjoyshmitz%2Fopenstef-reference?ref=badge_large)

# Licenses third-party libraries
This project includes third-party libraries, which are licensed under their own respective Open-Source licenses. SPDX-License-Identifier headers are used to show which license is applicable. The concerning license files can be found in the LICENSES directory.


# Contributing
Please read [CODE_OF_CONDUCT.md](https://github.com/OpenSTEF/.github/blob/main/CODE_OF_CONDUCT.md), [CONTRIBUTING.md](https://github.com/OpenSTEF/.github/blob/main/CONTRIBUTING.md) and [PROJECT_GOVERNANACE.md](https://github.com/OpenSTEF/.github/blob/main/PROJECT_GOVERNANCE.md) for details on the process for submitting pull requests to us.

## Contact
Please read [SUPPORT.md](https://github.com/OpenSTEF/.github/blob/main/SUPPORT.md) for how to connect and get into contact with the OpenSTEF project