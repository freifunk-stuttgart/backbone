# Install Wireguard on Debian 11

```
apt update
apt install wireguard
cd /etc/wireguard
wg genkey | tee wg-private.key | wg pubkey > wg-public.key
chmod 600 wg-private.key
```
add key to conf/wireguard-pubkeys
# Initial setup on backbone member
```
mkdir -p /var/lib/ffs; cd /var/lib/ffs; git clone https://github.com/freifunk-stuttgart/backbone.git
```
# Update
```
cd /var/lib/ffs/backbone/bin; git pull; ./create-config --bird; rsync -rlHpogDtSvcx ../output/etc /
birdc configure check
birdc configure
birdc show protocols
birdc6 configure check
birdc6 configure
birdc6 show protocols
```
