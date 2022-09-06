# Sitecore Docker Examples for JSS and React

This repository is a fork of https://github.com/Sitecore/docker-examples. It includes additional modules and configuration files for running Sitecore JSS for React using Docker containers (see `custom-images`).

Summary of changes:
* Headless services module is included into CM and CD images
* Additional container for the Rendering Host to support Experience Editor (see `custom-images/docker-compose.yml` and `custom-images/docker-compose.override.yml`)
* Additional container for the SSR proxy in connected mode  for the front-end requests (see `custom-images/docker-compose.yml` and `custom-images/docker-compose.override.yml`)
* New variables in `.env` file

Briefly, here's what you'll find in this repo:

* Example for running an out of the box Sitecore instance (see `getting-started`).
* Example solution for creating custom Sitecore images, with recommended folder structure for container development (see `custom-images`).
* Sample PowerShell scripts for container-based Sitecore instance preparation (`init.ps1`) and cleanup (`clean.ps1`).
* Docker compose files for building Sitecore instances in various topologies (see `custom-images`).

Please refer to the [Sitecore Containers documentation](https://containers.doc.sitecore.com/) for complete details, including running the examples and recommended usage.
