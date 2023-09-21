<p align="center">
  <a href="https://umbrel.com">
    <img src="https://i.imgur.com/7Fd0HJy.jpg" alt="Logo">
  </a>
  <h1 align="center">Nostr Relay for Umbrel for RPI</h1>
  <p align="center">
    Original from <a href="https://github.com/getumbrel/umbrel-nostr-relay">umbrel-nostr-relay</a> This repository is building for RaspberryPI arm architecture only.<br/>
    Run your private Nostr relay to backup all your activity on Nostr. An official app by Umbrel. Powered by <a href="https://github.com/scsibug/nostr-rs-relay">nostr-rs-relay</a>.
    <br />
    <a href="https://umbrel.com"><strong>umbrel.com »</strong></a>
    <br />
    <br />
    <a href="https://twitter.com/umbrel">
      <img src="https://img.shields.io/twitter/follow/umbrel?style=social" />
    </a>
    <a href="https://t.me/getumbrel">
      <img src="https://img.shields.io/badge/community-chat-%235351FB">
    </a>
    <a href="https://reddit.com/r/getumbrel">
      <img src="https://img.shields.io/reddit/subreddit-subscribers/getumbrel?style=social">
    </a>
    <a href="https://community.getumbrel.com">
      <img src="https://img.shields.io/badge/community-forum-%235351FB">
    </a>
  </p>
</p>

## Getting started

This app repository using docker and docker-compose to start nostr relay with 1 command line
```bash
#change config in data/relay/config.toml
docker compose up -d
```
Enjoy your home RaspberryPi as a Nostr relay

** You can setup DNS and reverse proxy for this relay [nginx-reverse-proxy](https://nolifelover.medium.com/create-a-reverse-proxy-for-your-application-using-nginx-and-certbot-25fe971682c6)
```
#example for reverse proxy th2.nostr.earnkrub.xyz
server {
 server_name th2.nostr.earnkrub.xyz;
 access_log /var/log/nginx/th2.nostr.earnkrub.xyz.access.log;
 error_log /var/log/nginx/th2.nostr.earnkrub.xyz.error.log;

 location / {
  proxy_pass http://127.0.0.1:3000;
  proxy_http_version 1.1;
  proxy_set_header Upgrade $http_upgrade;
  proxy_set_header Connection "Upgrade";
  proxy_set_header Host $host;
 }
}
```

By running your personal Nostr Relay on your Umbrel, you can connect your Nostr clients, such as Damus, Astral, and Amethyst, to your private relay for seamless backup of all your activity on Nostr. This ensures that your activity is not lost even if you are censored or blocked by public relays.

In Damus, go to Settings > Relays to add your Relay URL.

> Tip: Install Tailscale on your Umbrel and your devices for an uninterrupted connection between your clients and your relay, even when you're away from your home network. Enable Tailscale's MagicDNS and use ws://umbrel:4848 as your Relay URL.

Nostr Relay is powered by the open source [nostr-rs-relay](https://github.com/scsibug/nostr-rs-relay) project — a Rust implementation of Nostr relay. It currently supports the entire relay protocol, including NIP-01, NIP-02, NIP-03, NIP-05, NIP-09, NIP-11, NIP-12, NIP-15, NIP-16, NIP-20, NIP-22, NIP-26, NIP-28, and NIP-33.

---

[![License](https://img.shields.io/github/license/getumbrel/umbrel-nostr-relay?color=%235351FB)](https://github.com/getumbrel/umbrel-nostr-relay/blob/master/LICENSE.md)

[umbrel.com](https://umbrel.com)
