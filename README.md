# Slack Scalable Bot

This is a basic implementation of Slack bot <<description>>

## ToDo
* Add logic to suggest release or tweet over interval of time
* Do something with tokens saved in Dockerfile
* Async execution in main module


## Docker
* Docker compose:
```bash
# Build container and start
docker-compose up
# Stop containers
docker-compose stop
```
* Individual container:
```bash
# Check if Docker is installed
docker version
# Remove existing container
docker rm slack-bot
# Build
docker build --tag slack-bot .
# Run
# -d    start as daemon
docker run --name slack-bot slack-bot
or to expose Flask
docker run --name slack-bot -p 65010:65010 slack-bot
```

```bash
# Execute command in container
docker exec -it slack-discogs-bot /bin/sh
# View container logs
docker logs <<container>>
# Start container
docker start <container>
# Stop container
docker stop <container>
# View internal container IP address
docker inspect <<container>> | grep Address
```

## Development

Only AWS specific environment variables should be setup in development 
environment and server side:
* AWS_REGION_NAME
* AWS_ACCESS_KEY_ID
* AWS_SECRET_ACCESS_KEY

Add persistent environment variables on dev box:
```bash
sudo -H gedit /etc/environment
```

Everything else is pulled from DynamoDb.

## Tokens

### Bot
Generate token - [Slack Apps](https://api.slack.com/apps)
* SLACK_BOT_TOKEN
* SLACK_CLIENT_ID
* SLACK_CLIENT_SECRET
* SLACK_OAUTH_ACCESS_URL

### Services
* <<SERVICE_NAME>>_CLIENT_ID
* <<SERVICE_NAME>>_CLIENT_SECRET\
[Discogs](https://www.discogs.com/settings/developers)\
[Twitter](https://developer.twitter.com/en/apps)\
[Mixcloud](https://www.mixcloud.com/developers/)

## Balena Cloud
Bot is running in Docker environment on Raspberry Pi v4.
For quick and easy deployment BalenaOS is used on the device and BalenaCLI is required to deploy code to the cloud and build docker images:
[Balena CLI](https://github.com/balena-io/balena-cli/blob/master/INSTALL.md)
```bash
balena push <<aplication_name>>
```

## Useful links
[Discogs API Client](https://github.com/discogs/discogs_client)

[Discogs OAuth Example](https://github.com/jesseward/discogs-oauth-example)

[Instagram Authentication](https://www.instagram.com/developer/authentication/)

[Slack - Block Kit Builder](https://api.slack.com/tools/block-kit-builder)

[Slack - Unfurling Links In Messages](https://api.slack.com/docs/message-link-unfurling#classic_unfurling)

[Slack API Home](https://api.slack.com/)

[Slack API - Python](https://python-slackclient.readthedocs.io/en/latest/index.html)
## License
[MIT](https://choosealicense.com/licenses/mit/)
