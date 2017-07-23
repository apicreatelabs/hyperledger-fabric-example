## Install

```bash
npm install -g ts-node typescript
```

```bash
npm install
```

## Help

To see what are the commands that are available issue:

```bash
npm run info
```

#### Generating the crypto material for all the organizations


See [Bootstrapping the Hyperledger Fabric Network (Part 1)](https://ksachdeva.github.io/2017/07/21/bootstrapping-hyperledger-fabric-nw-1/)

```bash
cryptogen generate --config=./crypto-config.yaml
```

#### Generating the Orderer genesis block

See [Bootstrapping the Hyperledger Fabric Network (Part 2)](https://ksachdeva.github.io/2017/07/21/bootstrapping-hyperledger-fabric-nw-2/)

```bash
configtxgen -profile ThreeOrgsOrdererGenesis -outputBlock ./genesis.block
```

You can directly use the docker-compose command as specified in the blog post or using the command that I have hooked up in the package.json. The npm command also deletes 'production' folder so that every time your start the orderer node it starts with clean content.

```bash
npm run start-containers
```

Similarly to stop the containers simply issue

```bash
npm run stop-containers
```

#### Generating the channel configuration transaction

See [Bootstrapping the Hyperledger Fabric Network (Part 3)](https://ksachdeva.github.io/2017/07/22/bootstrapping-hyperledger-fabric-nw-3/)

```bash
configtxgen -profile ThreeOrgsChannel -outputCreateChannelTx ./ksachdeva-exp-channel-1.tx -channelID ksachdeva-exp-channel-1
```
