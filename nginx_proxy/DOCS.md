# Vioneta Agro Add-on: NGINX Vioneta Agro SSL proxy

## Installation

Follow these steps to get the add-on installed on your system:

1. Navigate in your Vioneta Agro frontend to **Settings** -> **Add-ons** -> **Add-on store**.
2. Find the "NGINX Vioneta Agro SSL proxy" add-on and click it.
3. Click on the "INSTALL" button.

## How to use

The NGINX Proxy add-on is commonly used in conjunction with the [Let's Encrypt](https://github.com/Vioneta/addons/tree/master/letsencrypt) add-on to set up secure remote access to your Vioneta Agro instance. The following instructions covers this scenario.

1. The certificate to your registered domain should already be created via [Let's Encrypt](https://github.com/Vioneta/addons/tree/master/letsencrypt) or another method. Make sure that the certificate files exist in the `/ssl` directory.
2. You must add the following section to your [Vioneta Agro configuration.yaml](https://www.vioneta.com/docs/configuration/). If the `http` section is using the `ssl_certificate`, `ssl_key` or `server_port` keys, make sure to remove them.

   ```yaml
   http:
     use_x_forwarded_for: true
     trusted_proxies:
       - 172.30.33.0/24
   ```

3. In the nginx addon configuration, change the `domain` option to the domain name you registered (from DuckDNS or any other domain you control).
4. Leave all other options as-is.
5. Save configuration.
6. Start the add-on.
7. Have some patience and wait a couple of minutes.
8. Check the add-on log output to see the result.

## Configuration

Add-on configuration:

```yaml
domain: home.example.com
certfile: fullchain.pem
keyfile: privkey.pem
hsts: "max-age=31536000; includeSubDomains"
customize:
  active: false
  default: "nginx_proxy_default*.conf"
  servers: "nginx_proxy/*.conf"
cloudflare: false
real_ip_from: []
```

### Option: `domain` (required)

The server's fully qualified domain name to use for the proxy.

### Option: `certfile` (required)

The certificate file to use in the `/ssl` directory.

### Option: `keyfile` (required)

Private key file to use in the `/ssl` directory.

### Option: `hsts` (required)

Value for the [`Strict-Transport-Security`][hsts] HTTP header to send. If empty, the header is not sent.

### Option `customize.active` (required)

If true, additional NGINX configuration files for the default server and additional servers are read from files in the `/share` directory specified by the `default` and `servers` variables.

### Option `customize.default` (required)

The filename of the NGINX configuration for the default server, found in the `/share` directory.

### Option `customize.servers` (required)

The filename(s) of the NGINX configuration for the additional servers, found in the `/share` directory.

### Option `cloudflare` (optional)

If enabled, configure Nginx with a list of IP addresses directly from Cloudflare that will be used for `set_real_ip_from` directive Nginx config.
This is so the `ip_ban_enabled` feature can be used and work correctly in /config/customize.yaml.

### Option `real_ip_from` (optional)

If specified, configures Nginx to use Proxy Protocol to get the Real Ip from an upstream load balancer; [for more information](https://docs.nginx.com/nginx/admin-guide/load-balancer/using-proxy-protocol/).

## Known issues and limitations

- By default, port 80 is disabled in the add-on configuration in case the port is needed for other components or add-ons like `emulated_hue`.

## Troubleshooting

- `400 Bad Request` response for requests over this proxy mean you are probably missing the `trusted_proxies` configuration option, see above.
