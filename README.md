# chat-environment
### Initial setup
##### Create .env file
```bash
echo -e "ROOT_URL=https://chat.example.com\nMAIL_URL=smtp://mail.example.com:25\nROCKETCHAT_URL=https://chat.example.com" > .env 
```

##### Init mongo replica
```bash
./scripts/launch.sh
docker exec chatenvironment_mongo_1 mongo --eval "rs.initiate({ _id: 'rs0', members: [ { _id: 0, host: '10.50.0.23:27017' } ]})"

docker start chatenvironment_rocketchat0_1
```

### Control
##### Start/restart environment
```bash
./scripts/launch.sh
```
