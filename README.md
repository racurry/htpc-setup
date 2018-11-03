# HTPC Set up

My complete set up for my home media server running on my Mac Mini.  All apps end up with custom subdomains like `app.domain.com` thanks to Traefik.

## Prerequisites
1. Docker

## Configure domain name
1. Register a domain name at namecheap.com
2. Set up host records
   1. Enable dynamic DNS.  Using your IP address, add
   2. A+ Dynamic DNS record -  @ - {IP address} - Automatic
   3. A+ Dynamic DNS record -  * - {IP address} - Automatic
3. Request API access - this takes a few business days.

## Keep domain pointed to your server
1. Install [dDNS broker](https://ddnsbroker.com)
2. Add entries for root (@) and wildcard subdomains (*)

## Configure port forwarding on your router
1. Point ports 80 and 443 to your Mac Mini in your router

## Prep
Run `./setup`

Fill out the .env file

Fill out email address, domain name in traefik/traefik.toml

Run `docker-compose up -d`

## Not covered
Plex is run separately.

## Credits
I mostly put this together by following [this guide](https://www.smarthomebeginner.com/traefik-reverse-proxy-tutorial-for-docker/) and this [one](https://github.com/duhio/docker-compose-usenet).
