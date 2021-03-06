+++
title = "Documentation"
date = 2020-07-06
draft = false
weight = 01
toc = false
+++

​
Everything you need to know about Tinkerbell and its major component microservices.

## What is Tinkerbell?

Tinkerbell is an open-source, bare metal provisioning engine, built and maintained by the team at Packet.

- Interested in collaborating? Join our growing community of [Contributors](/contributors) on [GitHub](https://github.com/tinkerbell) or [Slack](https://slack.packet.com)

## What's Powering Tinkerbell?

The Tinkerbell stack consists of five microservices, or components:

- [**Boots**](https://github.com/tinkerbell/boots) - Boots is Tinkerbell's DHCP server. It handles DHCP requests, hands out IPs, and serves up iPXE. It uses the Tinkerbell client to pull and push hardware data. It only responds to a predefined set of MAC addresses so it can be deployed in an existing network without interfering with existing DHCP infrastructure.

- [**Hegel**](https://github.com/tinkerbell/hegel) - Hegel is the metadata service used by Tinkerbell and OSIE. It collects data from both and transforms it into a JSON format to be consumed as metadata.

- [**OSIE**](https://github.com/tinkerbell/osie) - OSIE is an in-memory installation environment for bare metal. It installs operating systems and handles deprovisioning.

- [**PBnJ**](https://github.com/tinkerbell/pbnj) - PBnJ is a microservice that can communicate with baseboard management controllers (BMCs) to control power and boot settings.

- [**Tink**](https://github.com/tinkerbell/tink) - Tink is the Tinkerbell server and CLI. It communicates over gRPC, and is responsible for processing workflows. The CLI is used to create workflows and their building blocks, templates and hardware data.

In addition to the microservices, there are three pieces of infrastructure:

- [**PostgreSQL**](https://www.postgresql.org/) - Tinkerbell uses PostgreSQL as its data store. PostgreSQL is a free and open-source relational database management system, and it stores Tinkerbell's hardware data, templates, and workflows.

- [**Image Repository**](https://hub.docker.com/_/registry) - Tinkerbell uses a local image repository to store all of the action images used in a workflow. This is particularly useful for secure environments that don't have access to the internet. You can also choose to use [Quay](https://quay.io/) or [DockerHub](https://hub.docker.com/) as the repository if your environment does have internet access.

- [**NGINX**](https://www.nginx.com/) - NGINX is a web server which can also be used as a reverse proxy, load balancer, mail proxy, and HTTP cache. Tinkerbell uses NGINX to serve the required boot files during workflow execution.

## First Steps

New to Tinkerbell or bare metal provisioning? This is a great place to start!

- Getting Started - Set up Tinkerbell [locally with vagrant](/setup/local-with-vagrant/) or on [Packet with Terraform](/setup/packet-with-terraform/).
- Run [hello world](/examples/hello-world/) to see Tinkerbell in action.​

## Get Help

Need a little help getting started? We're here!

- Check out the [FAQs](/faq) - When there are questions, we document the answers.
- Join our [Community Slack](/community-slack).
- Submit an issue on [Github](https://github.com/tinkerbell/).
