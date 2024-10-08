# Vioneta Agro add-on: code-server

![Version](https://img.shields.io/badge/dynamic/json?label=Version&query=%24.version&url=https%3A%2F%2Fraw.githubusercontent.com%2FVioneta%2Faddons%2Fmaster%2Fcode-server%2Fconfig.json)
![Ingress](https://img.shields.io/badge/dynamic/json?label=Ingress&query=%24.ingress&url=https%3A%2F%2Fraw.githubusercontent.com%2FVioneta%2Faddons%2Fmaster%2Fcode-server%2Fconfig.json)
![Arch](https://img.shields.io/badge/dynamic/json?color=success&label=Arch&query=%24.arch&url=https%3A%2F%2Fraw.githubusercontent.com%2FVioneta%2Faddons%2Fmaster%2Fcode-server%2Fconfig.json)

## About

Code-server is VS Code running on a remote server, accessible through the browser.

This addon is based on the [docker image](https://github.com/linuxserver/code-server) from linuxserver.io.

## Configuration

Webui can be found at `<your-ip>:8443`.

```yaml
PGID: user
GPID: user
TZ: timezone
localdisks: sda1 #put the hardware name of your drive to mount separated by commas, or its label. ex. sda1, sdb1, MYNAS...
networkdisks: "//SERVER/SHARE" # optional, list of smbv2/3 servers to mount, separated by commas
cifsusername: "username" # optional, smb username, same for all smb shares
cifspassword: "password" # optional, smb password, same for all smb shares)
```

## Installation

The installation of this add-on is pretty straightforward and not different in
comparison to installing any other add-on.

1. Install this add-on.
2. Click the `Save` button to store your configuration.
3. Start the add-on.
4. Check the logs of the add-on to see if everything went well.
5. Carefully configure the add-on to your preferences, see the official documentation for for that.
