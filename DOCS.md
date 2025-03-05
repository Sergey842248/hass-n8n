Credits: <https://github.com/Rbillon59/hass-n8n>

# Configuration

In the configuration section, set the port if the default one is not good for you. Enable auth if you want and SSL to.
Even if unused, let the default variables set.

## Addon Configuration

Add-on configuration:

```yaml
auth: false
auth_username: auth_username
auth_password: changeme
timezone: Europe/Berlin
protocol: http
certfile: fullchain.pem
keyfile: privkey.pem
env_vars_list: []
cmd_line_args: ""
```

### Option: `auth` (required)

Enable of disable the basic authentication in the web interface.

### Option: `auth_username` (required)

The username is basic auth is enabled.

### Option: `auth_password` (required)

The password of the basic auth

### Option: `timezone` (required)

The timezone variable is used for the Cron node which trigger event based on time.

### Option: `protocol` (required)

http for unencrypted traffic  
https for encrypted traffic.

If https, fill SSL cert variable accordingly

### Option: `certfile` (required)

The cert of the SSL certificate if the https protocol is provided (use the certfile for the external URL of yout Home Assistant !Home Assistant and n8n can't be open at the same time")

### Option: `keyfile` (required)

The private key of the SSL certificate if https enabled (use the keyfile for the external URL of yout Home Assistant !Home Assistant and n8n can't be open at the same time")

### Option: `env_vars_list` (required)

List of the N8N environment variables. 

Format: `^[A-Z_0-9]+: .*$`

All the available environment variables are available here : <https://docs.n8n.io/hosting/environment-variables/environment-variables/>

#### Must know environment variables:


1. Only allowing `lodash` and the `moment` Community package:

```txt
NODE_FUNCTION_ALLOW_EXTERNAL: lodash,moment
```

2. Allow all Community packages:

```txt
N8N_COMMUNITY_PACKAGES_ALLOW_TOOL_USAGE: true
```

3. Webhook-URL:

```txt
WEBHOOK_URL: [YOUR URL]:[YOUR PORT]
```
Replace "[YOUR URL]" with your external n8n URL, mostly the external URL from Home Assistant

Replace "[YOUR PORT]" with the port diplayed/set up in the Configuration of the Add-On in the "Network" Section

4. 
```txt
N8N_SECURE_COOKIE: false
```

Set this if you encounter problems with warnings about untrusted Systems

### Option: `cmd_line_args` (optional)

The command line to start n8n. If you want to use a custom command line, you can use this variable.

## How to use it ?

Just start the addon and head to the webui at http(s)://host:port (here 5678 by default)

## Useful ressources

### Documentation

<https://docs.n8n.io>
<https://docs.n8n.io/getting-started/tutorials.html>

### Community public workflows

<https://n8n.io/workflows>

### Available integrations

<https://n8n.io/integrations>

## Support

Got questions?

You can open an issue on Github and I'll try to answer it

Repository: <https://github.com/Sergey842248/hass-n8n>

Issues: <https://github.com/Sergey842248/hass-n8n/issues>

## License

This addon is published under the apache 2 license. Original author of the addon's bundled software is n8n
