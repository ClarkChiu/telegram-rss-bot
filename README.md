# Telegram RSS Bot

## Feature

- Self-hosted RSSHub
- No expose port (No default listening port)

## Prerequisite

### Software

- [Docker][Docker Install]
- [Docker Compose][Docker Compose Install]

### Tokens

- [Telegram Bot token][Telegram Bot Apply]
- [Telegraph token (optional)][Telegraph Token Apply]

## Tech Stack

- [Flowerss]: A telegram bot for rss reader
- [RSSHub]: Everything is RSSible
- [docker-wait-for-dependencies][Docker-Compose-Wait]: Docker container that blocks until given endpoints are accessible over TCP

## Start

```shell
# Prepare the config file
cp flowerss/config.yml.sample flowerss/config.yml

# Complete the config file
vim flowerss/config.yml

# Start the services
$ sudo docker-compose run --rm wait_for_rsshub_service && \
sudo docker-compose up -d flowerss
```

## Note

### [RSSHub-Radar][RSSHub-Radar]

You can setting the http://rsshub:1200 as the domain in RSSHub-Radar directly. Docker compose auto creates the mapping of the service name and IP address in containers within same service. Therefore, the flowerss can access the host (i.e.: rsshub) via internal network.

[Docker Install]: <https://docs.docker.com/engine/install/>
[Docker Compose Install]: <https://docs.docker.com/compose/>

[Telegram Bot Apply]: <https://core.telegram.org/bots>
[Telegraph Token Apply]: <https://telegra.ph/api#createAccount>

[Flowerss]: <https://github.com/indes/flowerss-bot>
[RSSHub]: <https://github.com/DIYgod/RSSHub>
[Docker-Compose-Wait]: <https://8thlight.com/blog/dariusz-pasciak/2016/10/17/docker-compose-wait-for-dependencies.html>

[RSSHub-Radar]: <https://github.com/DIYgod/RSSHub-Radar>