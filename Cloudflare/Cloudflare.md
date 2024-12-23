# Cloudflare

## install：

### Debian

```
##server

curl -L --output cloudflared.deb https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb &&
sudo dpkg -i cloudflared.deb &&
sudo cloudflared service install token
```

## tunnel：

### http

#### config

- Public Hostname: sub-your-domain.your-domain
- Service: http://localhost:3000

#### connect

- http://sub-your-domain.your-domain

### ssh

#### config

- Public Hostname: sub-your-domain.your-domain
- Service: ssh://localhost:22

#### connect

- install client

```
##client

curl -L --output cloudflared.deb https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb &&
sudo dpkg -i cloudflared.deb &&
```

- ssh connect use ProxyCommand

```
ssh -o StrictHostKeyChecking=no -o ProxyCommand="/usr/local/bin/cloudflared access ssh --hostname %h" user@sub-your-domain.your-domain
```
