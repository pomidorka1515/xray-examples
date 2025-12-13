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
