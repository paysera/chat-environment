# chat-environment
### Initial setup
##### Create .env file
```bash
echo -e "ROOT_URL=https://chat.example.com\nMAIL_URL=smtp://mail.example.com:25\nROCKETCHAT_PASSWORD=botpassword\nROCKETCHAT_ROOM=GENERAL\nROCKETCHAT_USER=bot\nBOT_NAME=bot\nLISTEN_ON_ALL_PUBLIC=true\nEXTERNAL_SCRIPTS=hubot-help,hubot-links,hubot-standup-alarm" > .env 
```

### Control
##### Start/restart environment
```bash
./scripts/launch.sh
```
##### scale
```bash
docker-compose scale rocketchat=4
```
