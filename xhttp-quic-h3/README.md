# XHTTP over UDP (HTTP/3, QUIC)

# ⚠️ WARNING: DO NOT USE ON CELLULAR DATA.
## They throttle UDP heavily. Just don't, okay?
## Also dont use this in Russia, Iran, etc. They throttle HTTP/3 too.
# Perks
- UDP based, less delay
- if a packet gets lost, the whole stream isnt stalled
- good for gaming
# Cons
- your upload speed will drop, prepare for it. Couldn't find a workaround.
- trash on cellular
- some shitty ISPs might throttle udp on fiber too
# Requirements 
## Server
- xray-core latest stable version (v25.1x)
- optional but recommended, a panel for xray like 3x-ui and remnawave
- nginx latest version (1.29)
  - please note, apt package manager ships v1.24.x as latest version, make sure to change the repo to nginx`s one
  - critical!! quic isnt supported on old versions
- a domain which you own
  - it points to your vps ip adress
- valid ssl certificates
## Client 
- a client which supports xhttp
  - cant be based on mihomo or sing box, they don't support xhttp yet
- latest xray-core (v25.1x)
## Miscellaneous 
- a working brain yet again

## Files
- nginx.conf - your nginx configuration
- client.json(c) - your client configuration
- server.json(c) - your server configuration
