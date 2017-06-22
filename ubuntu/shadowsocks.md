# Install shadowsocks-libev
```
$ sudo apt-get install libmbedtls-dev
$ sudo apt-get install git
$ sudo apt-get install automake
$ sudo apt-get install --no-install-recommends build-essential autoconf libtool \
        libssl-dev gawk debhelper dh-systemd init-system-helpers pkg-config asciidoc \
        xmlto apg libpcre3-dev zlib1g-dev libev-dev libudns-dev libsodium-dev
$ git clone https://github.com/shadowsocks/shadowsocks-libev.git
$ cd shadowsocks-libev
$ git submodule update --init
$ ./autogen.sh && ./configure && make
$ sudo make install
```
# Create shadowsocks-server.service
/etc/shadowsocks/config.json
```
{
    "server":"server ip",
    "server_port":8388,
    "local_address": "127.0.0.1",
    "local_port":1080,
    "password":"password",
    "timeout":300,
    "method":"rc4-md5",
    "fast_open": false,
    "workers": 1
}

```
/etc/systemd/system/shadowsocks-server.service
```
[Unit]
Description=Shadowsocks Server
After=network.target

[Service]
ExecStart=/usr/local/bin/ss-server -c /etc/shadowsocks/config.json
Restart=on-abort

[Install]
WantedBy=multi-user.target
```
Run command `systemctl enable shadowsocks-server` and `systemctl start shadowsocks-server`
