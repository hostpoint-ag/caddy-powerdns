PowerDNS module for Caddy
===========================

This package contains a DNS provider module for [Caddy](https://github.com/caddyserver/caddy). It can be used to 
manage DNS records with PowerDNS.

## Config examples

To use this module for the ACME DNS challenge, [configure the ACME issuer in your Caddy JSON](https://caddyserver.com/docs/json/apps/tls/automation/policies/issuer/acme/) like so:

```json
{
	"module": "acme",
	"challenges": {
		"dns": {
			"provider": {
			"name": "powerdns",
			"api_token": "POWERDNS_API_TOKEN",
			"server_url": "https://your.powerdns.com",
			"server_id": "localhost"
			}
		}
	}
}
```

or with the Caddyfile:

```
# globally
{
	acme_dns powerdns {
		api_token POWERDNS_API_TOKEN
		server_url https://your.powerdns.com
		server_id localhost
	}
}
```

```
# one site
tls {
	dns powerdns {
		api_token POWERDNS_API_TOKEN
		server_url https://your.powerdns.com
		server_id localhost
	}
}
```
