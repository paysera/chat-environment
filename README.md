# chat-environment
### Initial setup
##### Create .env file
```bash
echo -e "ROOT_URL=https://chat.example.com\nMAIL_URL=smtp://mail.example.com:25\nROCKETCHAT_URL=https://chat.example.com" > .env 
```

##### Init mongo replica
```bash
./scripts/launch.sh
docker exec chat-environment_mongo_1 mongo --eval "rs.initiate({ _id: 'rs0', members: [ { _id: 0, host: '10.50.0.23:27017' } ]})"
docker exec chat-environment_mongo_1 mongo --eval "rs.add({ host: '10.50.0.20:27017', priority: 0, votes: 0 })"
docker exec chat-environment_mongo_1 mongo --eval "rs.add({ host: '10.50.0.21:27017', priority: 0, votes: 0 })"

docker start chat-environment_rocketchat_1
```

### Control
##### Start/restart environment
```bash
./scripts/launch.sh
```
