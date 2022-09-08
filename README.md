# Sitecore Docker Examples for JSS and React

This repository is a fork of https://github.com/Sitecore/docker-examples. It includes additional modules and configuration files for running Sitecore JSS for React using Docker containers (see `custom-images`), including Experience Editor support.

Summary of changes:
* Headless services module is included into CM and CD images
* Custom `nanoserver` image is added for NodeJS roles. This was required because JSS app for React uses an npm package called "open" and the package contains a hardcoded path to Powershell exe which does not exist in Nanoserver. The standard Microsoft Nanoserver is extended with Powershell package copied to `C:\Windows\System32\WindowsPowerShell\v1.0`.
Note: Sitecore roles use the standard Nanoserver directly from Microsoft repository.
* Additional container `rendering` for the Rendering Host to support Experience Editor (see `custom-images/docker-compose.yml` and `custom-images/docker-compose.override.yml`)
* Additional container `ssrproxy` for the SSR proxy in connected mode  for the front-end requests (see `custom-images/docker-compose.yml` and `custom-images/docker-compose.override.yml`)
* New variables in `.env` file
* Ngrok support:
    * The custom Nanoserver image includes `/Windows/System32/NetApi32.dll` to support Ngrok
    * Ngrok-related code can be uncommented in `\scripts\http-renderer.js`, it is disabled by default for two reasons:
        * it requires an account and authentication key from this account to be installed within container before it can run
        * it generates a different domain each time container starts and it's not very helpful for the Experience Editor scenario because CM needs to know this domain in advance

Briefly, here's what you'll find in this repo:

* Example for running an out of the box Sitecore instance (see `getting-started`).
* Example solution for creating custom Sitecore images, with recommended folder structure for container development (see `custom-images`).
* Sample PowerShell scripts for container-based Sitecore instance preparation (`init.ps1`) and cleanup (`clean.ps1`).
* Docker compose files for building Sitecore instances in various topologies (see `custom-images`).

Please refer to the [Sitecore Containers documentation](https://containers.doc.sitecore.com/) for complete details, including running the examples and recommended usage.
