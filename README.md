# chat-environment
### Initial setup
##### Create .env file
```bash
echo -e "ROOT_URL=https://chat.example.com\nMAIL_URL=smtp://mail.example.com:25\nROCKETCHAT_URL=https://chat.example.com\nROCKETCHAT_PASSWORD=botpassword\nROCKETCHAT_ROOM=GENERAL\nROCKETCHAT_USER=bot\nBOT_NAME=bot\nLISTEN_ON_ALL_PUBLIC=true\nEXTERNAL_SCRIPTS=hubot-help,hubot-links,hubot-standup-alarm,hubot-giphy,hubot-redis-brain,hubot-seen,hubot-diagnostics,hubot-bofh,hubot-bookmark,hubot-shipit,hubot-maps" > .env 
```
##### Create .proxy_env file
```bash
echo -e "VIRTUAL_HOST=chat.example.com\n" > .proxy_env 
```

### Control
##### Start/restart environment
```bash
./scripts/launch.sh
```

### Plugins
##### Create .plugins file
```bash
echo -e "\${DOCKER_BIN_DIRECTORY}/docker exec -it chatenvironment_hubot_1 npm install hubot-giphy --save\n" > .plugins 
```
##### Add plugin to .env file
```bash
sed -i '/^EXTERNAL_SCRIPTS/ s/$/,hubot-giphy/' .env
```
