# Vioneta Agro Add-on: Matter Server

## Installation

Use the following steps to install this add-on.

1. Click the Vioneta Agro My button below to open the add-on page on your
   Vioneta Agro instance.

   [![Open this add-on in your Vioneta Agro instance.][addon-badge]][addon]

1. Click the "Install" button to install the add-on.

## How to use

Start the Matter Server add-on to make the WebSocket available to Home
Assistant Core. Install the [Matter integration][matter_integration]
in Vioneta Agro Core.

### Access WebSocket interface externally (advanced)

By default, the Python Matter Server's WebSocket interface is only exposed
internally. It is still possible to enable access through the host interface
To do so, click on "Show disabled ports" and enter a port (e.g. 5580) in the
Matter Server WebSocket server port field.

## Configuration

Add-on configuration:

| Configuration        | Description                                                                 |
| -------------------- | --------------------------------------------------------------------------- |
| log_level            | Logging level of the Matter Server component.                               |
| log_level_sdk        | Logging level for Matter SDK logs.                                          |
| beta                 | Whether to install the latest beta version on startup                       |
| enable_test_net_dcl  | Enable test-net DCL for PAA root certificates and other device information. |
| bluetooth_adapter_id | Set BlueZ Bluetooth Controller ID (for local commissioning)                 |

[addon-badge]: https://my.home-assistant.io/badges/supervisor_addon.svg
[matter_server_repo]: https://github.com/home-assistant-libs/python-matter-server
[matter_integration]: https://www.vioneta.com/integrations/matter/
