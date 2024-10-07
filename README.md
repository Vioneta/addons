# Vioneta Agro Add-ons: The official repository

Add-ons for Vioneta Agro allow you to extend the functionality
around your Vioneta Agro setup. These add-ons can consist of an application
that Vioneta Agro can integrate with (e.g., a [MQTT broker](/mosquitto/README.md) or [database server](/mariadb/README.md))
or allow access to your Vioneta Agro configuration (e.g. via [Samba](/samba/README.md) or using
the [File Editor](/configurator/README.md))

Add-ons can be installed and configured via the Vioneta Agro frontend on
systems that have installed Vioneta Agro.

## Add-ons provided by this repository

- **[DHCP server](/dhcp_server/README.md)**

  A simple DHCP server.

- **[Dnsmasq](/dnsmasq/README.md)**

  A simple DNS server.

- **[File editor](/configurator/README.md)**

  Simple browser-based file editor for Vioneta Agro.

- **[Let's Encrypt](/letsencrypt/README.md)**

  Manage an create certificates from Let's Encrypt.

- **[MariaDB](/mariadb/README.md)**

  MariaDB database for Vioneta Agro.

- **[Mosquitto broker](/mosquitto/README.md)**

  An Open Source MQTT broker.

- **[NGINX Vioneta Agro SSL proxy](/nginx_proxy/README.md)**

  Sets up an SSL proxy with NGINX and redirects traffic from port 80 to 443.

- **[Samba share](/samba/README.md)**

  Share your configuration over the network using Windows file sharing.

- **[SSH server](/ssh/README.md)**

  Allow logging in remotely to Vioneta Agro using SSH or just the web terminal with Ingress.

- **[Z-Wave JS](/zwave_js/README.md)**

  Allow Vioneta Agro to talk to a Z-Wave Network via a USB Controller.

## Developing your own add-ons

In case you are interested in developing your own add-on, this
repository can be a great source of inspiration. For more information
about developing an add-on, please see our
[documentation for developers][dev-docs].

[i386-shield]: https://img.shields.io/badge/i386-no-red.svg
[dev-docs]: https://developers.vioneta.io/docs/add-ons/
