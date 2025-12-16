# VLESS + XHTTP + TLS (except it looks like gRPC!)

As we all know, gRPC transport is really stealhy. 
However, it's speeds suck, and the latency is insane.
That's why we are going to use XHTTP, a much more flexible and customizable transport.
## Little warning about upload speed
We use XHTTP+Nginx, and gRPC isnt standard http/2: so, your upload speed will be slower. Not critical tho, download is fine. Check buffer settings for customisation.
# Requirements
## Server
- xray-core latest stable version (v25.1x)
- optional but recommended, a panel for xray like 3x-ui and remnawave
- nginx latest version (1.29)
  - please note, apt package manager ships v1.24.x as latest version, make sure to change the repo to nginx`s one
- a domain which you own
  - it points to your vps ip adress
- valid ssl certificates
## Client 
- a client which supports xhttp
  - cant be based on mihomo or sing box, they don't support xhttp yet
- latest xray-core (v25.1x)
## Miscellaneous 
- a working brain
# Why use this complex setup?
- much more stable
- higher speeds
- better ping
- no extra unnecessary libraries unlike gRPC
- better support & isnt being deprecated

# Files
- nginx_config - your webservers config
- client.json - client configuration
- server.json - server configuration
# To get into this, take a look at the files!
