# HTPC Set up

A full HTPC home server running on a Mac Mini.

## Configure domain name
1. Register a domain name at namecheap.com
2. Set up host records
  a. Enable dynamic DNS.  Using your IP address, add
  a. A+ Dynamic DNS record -  @ - {IP address} - Automatic
  a. A+ Dynamic DNS record -  * - {IP address} - Automatic

## Keep domain pointed to your server
2. Install [dDNS broker](https://ddnsbroker.com)

## Port forwarding on your router
Open up 80, 443

## Get everything installed
Follow [this guide](https://www.smarthomebeginner.com/traefik-reverse-proxy-tutorial-for-docker/)

## Prep
Run `./setup`

Fill out the .env file

Fill out email address, domain name in traefik/traefik.toml