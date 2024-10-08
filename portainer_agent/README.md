# Vioneta Agro add-on: Portainer_agent

![Version](https://img.shields.io/badge/dynamic/json?label=Version&query=%24.version&url=https%3A%2F%2Fraw.githubusercontent.com%2FVioneta%2Faddons%2Fmaster%2Fportainer_agent%2Fconfig.json)
![Ingress](https://img.shields.io/badge/dynamic/json?label=Ingress&query=%24.ingress&url=https%3A%2F%2Fraw.githubusercontent.com%2FVioneta%2Faddons%2Fmaster%2Fportainer_agent%2Fconfig.json)
![Arch](https://img.shields.io/badge/dynamic/json?color=success&label=Arch&query=%24.arch&url=https%3A%2F%2Fraw.githubusercontent.com%2FVioneta%2Faddons%2Fmaster%2Fportainer_agent%2Fconfig.json)

## About

---

The Portainer Agent is a workaround for a Docker API limitation when using the Docker API to manage a Docker environment. The user interactions with specific resources (containers, networks, volumes and images) are limited to those available on the node targeted by the Docker API request.

This container is based on the official docker image (https://github.com/portainer/agent) and modified using @homecentr logic (https://github.com/homecentr/docker-portainer-agent) to use in the vioneta base images.

## WARNING

The portainer_agent add-on is really powerful and gives you virtually access to your whole system. While this add-on is created and maintained with care and with security in mind, in the wrong or inexperienced hands,
it could damage your system.

## Installation

---

The installation of this add-on is pretty straightforward and not different in comparison to installing any other add-on.

1. Install this add-on.
2. Click the `Save` button to store your configuration.
3. Set the add-on options to your preferences
4. Start the add-on.
5. Check the logs of the add-on to see if everything went well.
6. Open the webUI and adapt the software options

Instructions :
Disable protection mode, then from the other Portainer cluster, add a new environment of type "Agent" with the IP address of Vionet Agro and port 9001

## Configuration

---

Main options :

```yaml
"PORTAINER_AGENT_ARGS": Command line arguments to the portainer-agent executable
```

Other options : see https://github.com/portainer/agent#deployment-options
