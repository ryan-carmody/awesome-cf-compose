# Awesome CF compose  [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of Docker Compose examples for use with the ColdFusion Docker images, whether those from Adobe, or the Ortus CommandBox images for CF or Lucee, or the Lucee images. This effort is based on the concept found in the more general-purpose https://github.com/docker/awesome-compose project, but has been created separately to focus aspects of on CF-oriented container  processing.

These examples provide a starting point for how to integrate different services using a Compose file and to manage their deployment with Docker Compose.

Initially I planned this to be just about the Adobe CF Docker images, but I appreciate how those using the other types of CF images could not only benefit from but also bring energy and contribution to this effort.

A challenge will be how to clarify which compose files are suited to the ACF vs Ortus CF or Lucee vs Lucee images. I haven't decided yet if that's best done by separate folders, or indications in the compose file name. I'm leaning toward folders. Even then, this could be a challenge to manage, but let's go for it!

For now, the lists below are from my initial effort that was laying out how to show use of the ACF images. The lists will evolve to more clearly cover all 3 kinds of images, where appropriate.

## Contents
- [Example Docker Compose files for ColdFusion configuration variations](Example-Docker-Compose-files-for-ColdFusion-configuration-variations)
- [Examples of Docker feature enablement](Examples-of-Docker-feature-enablement)
- [Examples of integrated services](Examples-of-integrated-services)
- [Getting started](#Getting-started)
- [Considerations regarding configuration](#Considerations-regarding-configuration)
- [Many kinds of examples planned](#Many-kinds-of-examples-planned)
- [Contribute](#Contribute)

## Example Docker Compose files for ColdFusion configuration variations
- [`ColdFusion`](https://github.com/carehart/awesome-cf-compose/tree/master/coldfusion) (base CF image, latest image)
- ColdFusion 2018 
- ColdFusion 2016 
- ColdFusion 2018 Update 1 (how to indicate update level)
- ColdFusion with setup script enabled
- ColdFusion with admin config via CAR file
- ColdFusion with secure profile enabled
- ColdFusion with mysql jar embedded

### Examples of CF feature enablement
- ColdFusion with Solr feature enabled
- ColdFusion with PDFg (CFHTML2PDF) feature enabled
- ColdFusion with Redis sessions enabled

### Examples of related feature enablements
- ColdFusion with PMT enabled
- ColdFusion with API Manager enabled

## Examples of Docker feature enablement
- ColdFusion with CF webroot copied into image
- ColdFusion with CF webroot as host bind mount
- ColdFusion with CF webroot as Docker volume

## Examples of integrated services

### Examples of web server integration
- ColdFusion with Apache web server
- ColdFusion with IIS web server
- ColdFusion with nginx web server

### Examples of database integration
- ColdFusion with MySQL
- ColdFusion with SQL Server
- ColdFusion with Postgres
- ColdFusion with MongoDB

### Examples of reverse proxies/load balancers
- ColdFusion with Varnish
- ColdFusion with Squid
- ColdFusion with Traefik

### Other integrations
- ColdFusion with ?

### Examples of multiple integrated services
- ColdFusion with ?

## Getting started

These instructions will get you through the bootstrap phase of creating and deploying examples of containerized applications with Docker Compose.

### Prerequisites

- Make sure that you have Docker and Docker Compose installed
  - Windows or macOS:
    [Install Docker Desktop](https://www.docker.com/get-started)
  - Linux: [Install Docker](https://www.docker.com/get-started) and then
    [Docker Compose](https://github.com/docker/compose)
- Download some or all of the examples from this repository.

### Running an example

The root directory of each example contains the `docker-compose.yaml` which
describes the configuration of service components. All examples can be run in
a local environment by going into the root directory of each one and executing:

```console
docker-compose up -d
```

Check the `README.md` of each example to get more details on the structure and expected output, if any.

To stop and remove the all containers of the example application, run:

```console
docker-compose down
```

## Considerations regarding configuration

Whether using or contributing to the repository, note  the following considerations.

### Limiting the combinations of examples
It would be tempting to create compose files that combine many things at once (intergration of CF with Apache and mysql, or CF/Apache/mysql and the PMT, or CF/Apache/mysql and FR, or swapping out mysql for SQL Server, or IIS for Apache, and so on). 

Because the number of such combinations could grow exponentially (and become clumsy to manage as a folder structure), there will be many cases where a given facet of intergration will be demonstrated only once, in a single compose file, leaving the reader to take that information to bring together unique combinations on one or more other integrations which they may be interested to use. 

Time will tell how to best organize when contributors may offer examples combining several intergrations in one compose file.

### Some examples will presume dependencies and so not be self-contained
While many integrations will be shown using resources ALSO found in the compose file (making it self-contained), as is the normal expectation for compose files, some examples will be setup presuming instead to integrate with some resource existing OUTSIDE of the compose file, such as a mysql server defined on or in the network of the host. 

Such examples are necesary to meet real-world requirements as folks explore CF Docker images and integrations. Obviously, such examples will have dependencies which, if not existing, will cause the compose file to fail. 

### Use of volumes or bind mounts
Similarly, some examples will demonstrate integration with Docker volumes (defined in the compose file) while others may demonstrate using bind-mount volumes that refer to host resources outside the docker file which again, if not existing, will cause the compose file to fail. Comments in the compose file or readme should clarify such expected dependencies, if they are not self-evident.

## Many kinds of examples planned
In this project, the focus will be on examples of the many kinds of intergrations that are possible and potentially useful for users of ColdFusion, ranging from optional web servers that can front it, to back-end databases resources it can intergrate with, such as databases and caching engines--whether leveraging such integrations built-in to CF or not. 

The project is also expected to include examples of integrating with things like the ColdFusion API Manager (since CF2016 Enterprise) and the ColdFusion Performance Monitoring Toolkit (since CF2018 Standard and Enterprise), as well as demonstrations of implementation of other monitoring solutions, such as FusionReactor, SeeFusion, and other APMs.

[Contributions](#Contributions) are welcome.



<!--lint disable awesome-toc-->
## Contribute

We welcome examples that help people understand how to use Docker Compose for common applications. Check the [Contribution Guide](CONTRIBUTING.md) for more details. 
