# Install Wireguard on Debian 10

```
echo "# for wireguard" > /etc/apt/sources.list.d/bullseye.list
echo "deb http://deb.debian.org/debian/ bullseye main" >> /etc/apt/sources.list.d/bullseye.list
printf 'Package: *\nPin: release n=bullseye\nPin-Priority: 90\n' > /etc/apt/preferences.d/limit-bullseye
apt update
apt install wireguard
cd /etc/wireguard
wg genkey | tee wg-private.key | wg pubkey > wg-public.key
chmod 600 wg-private.key
```
