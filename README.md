# My HTPC

My complete set up for my home media server running on my Mac Mini.  All apps end up with custom subdomains like `app.domain.com` thanks to Traefik.

## Setup

### Prerequisites
1. Docker
2. A domain registered at namecheap.com
3. Port forwarding on your router, forwarding ports `80` and `443`

### Configure domain name
Turn on dynamic DNS at namecheap.com

### Configure the .env
1. `cp .env.example .env`.
2. Update `DOMAIN` to your actual domain.
3. Set the `HTPASSWD` value.  Use [this generator](http://www.htaccesstools.com/htpasswd-generator/)

### Set up traefik
1. `mkdir -p config/traefik`
2. `touch config/traefik/acme.json`
3. `chmod 600 config/traefik/acme.json`
4. `cp traefik.toml.example config/traefik/traefik.toml`
5. Set the correct email address in `config/traefik/traefik.toml`

### Set up ddconf
1. `mkdir -p config/ddclient`
2. `cp ddclient.conf.example config/ddclient/ddclient.conf`
3. Update the domain names and dynamic DNS password in `config/ddclient/ddclient.conf`

## Running
Run `docker-compose up -d`

You should now be able to get to everything by navigating to `app.your.domian`.

## Credits
This is largely identical to [https://github.com/duhio/docker-compose-usenet)](https://github.com/duhio/docker-compose-usenet)).

I also pulled some tips from [this smarthomebeginner.com guide](https://www.smarthomebeginner.com/traefik-reverse-proxy-tutorial-for-docker/).
