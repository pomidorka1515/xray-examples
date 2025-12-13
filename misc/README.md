# Enable BBR, change TCP buffer size

## BBR
```bash
sudo sysctl -w net.ipv4.tcp_congestion_control=bbr
>>> net.ipv4.tcp_congestion_control=bbr

sudo sysctl -w net.core.default_qdisc=fq
>>> net.core.default_qdisc=fq
```
## Change buffer
```bash
sudo sysctl -w net.ipv4.tcp_notsent_lowat=32768
>>> net.ipv4.tcp_notsent_lowat=32768
```
## Tips
- enable bbr on both client and server
- tweak buffer size on client
- keep buffer values divisible by 8

# Install latest Nginx version on Ubuntu/Debian
## Remove old nginx
```bash
sudo apt remove nginx nginx-common nginx-core
sudo apt autoremove
```
## Install prerequisites
```bash
sudo apt install curl gnupg2 ca-certificates lsb-release wrapper
```
## Import the Nginx signing key
```bash
curl -fsSL https://nginx.org/keys/nginx_signing.key | sudo gpg --dearmor -o /usr/share/keyrings/nginx-archive-keyring.gpg
```
## Add the repo (run as 1 command)
```bash
echo "deb [signed-by=/usr/share/keyrings/nginx-archive-keyring.gpg] \
http://nginx.org/packages/mainline/ubuntu `lsb_release -cs` nginx" \
| sudo tee /etc/apt/sources.list.d/nginx.list
```
## Update apt cache
```bash
sudo apt update
```
## Install nginx
```bash
sudo apt install nginx
```
# Get valid SSL certificates for TLS security
## Install certbot
```bash
sudo apt install certbot
```
## Point your domain to your IP adress
### IPv4
- in your registrar DNS settings, cludflare dns settings, etc: make an `A` record
- set the value to your VPS ipv4 adress
- if using cloudflare, dont set `Proxy through Cloudflare`
### IPv6
- same as IPv4, but you need to create an `AAAA` record instead
- and set the value to your VPS ipv6 adress
- dont only set an `AAAA` record, this isnt a good practice
## Get the certificate
```bash
sudo certbot certonly --standalone -d your-domain.com
```
## Files
- public key: `/etc/letsencrypt/live/your-domain.com/fullchain.pem`
- private key: `/etc/letsencrypt/live/your-domain.com/privkey.pem`
## Important information
- your public key is accessible to everyone, isnt a secret and safe to share *(even tho thats useless)*
- your private key, however, isnt for everyone, **and you should NOT share it.** if someone obtains this, they can impersonate your website.
- lets encrypt has a limit for issuing certificates, dont spam their servers if you dont want to get banned
- use a valid email for creating an account
- dont close port 80, 443 and 8443 - they are used to renew your certificates automatically
