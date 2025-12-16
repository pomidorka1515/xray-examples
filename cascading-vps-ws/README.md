# hi if ur seeing this then im sleeping (finishing soon ok pls wait thx)

# Cascading VPN (via WebSockets + TLS)

**hello! this is by far the most powerful AND stealthy setup to cirvumvent censorship.**
## how it works? theres 4 stages!
- client
- server 1 (located in, for example Russia/Iraq)
- server 2 (exit node, for example Germany/Finland/Netherlands/etc.)
- digital freedom!!!!
## scheme
you (client) -> _websocket+tls transmission_ -> server 1 -> _websocket+tls transmission_ -> server 2 (exit node) -> internet
# why is it so effective?
- most censors see constant foreign traffic (even if its valid TLS with real certificates) as "suspicious", you may experience throttling if set up incorrectly
- the most fancy thing, **CIDR based censoring bypass**. yea you do need server 1 from allowed subnets, but still
# requirements (**important**)
- two servers
  - 1st server location: in your country (russia/iraq)
  - 2nd server location: pretty much anywhere, i recommend eu locations tho (this is your exit node)
- nginx in front instead of xray on both servers 
  - latest version
- latest xray-core
- a client
  - can be based on mihomo too, we dont need xhttp (fuck you sing-box)
- a working brain ofc
- READ THIS:
  - to bypass "whitelists" in russia, you need an vps with an ip from allowed subnets
  - the bad news are, today almost all such ips are taken by other people, the chance to get one is extemely low now
  - juuust for reference: [yandex cloud](https://yandex.cloud/en), [vk cloud](https://cloud.vk.com/en/main/)
# files
- client.json(c) - client configuration
- server1.json(c) - server 1 configuration
- server2.json(c) - server 2 (exit node) configuration
- nginx1.conf - server 1 nginx config
- nginx2.conf - server 2 (exit node) nginx config
