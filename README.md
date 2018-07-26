# About
This branch contains the source code of xWallet, a customized crypto currency wallet for the project ["The X Company"](http://the-x-company.surge.sh/).

We decided to create our own crypto wallet since we need a customized solution to help us with our transactions and a better way to monitoring multi-balances and mining process.

The prototype system of xWallet contains 3 servers, one for Geth CLI, one for Mining tasks, the last one is for front-end application which was built using Meteor framework (NodeJS).

We also using MongoDB as 1 centralized DB (for performance-experiment purpose only)

You can check the user interface of the wallet [here](https://x-wallet.herokuapp.com/dashboard).

## How To Use
* Please change the setting of the file: the-x-company/x-wallet/client/lib/init.js
```
line 7:   web3.setProvider(new web3.providers.HttpProvider( ${your own Geth/RPC Server IP Address}) );
```

* Below is the command that we use to start our Geth Process.
```
$ nohup geth --testnet --nodiscover --rpc --rpcaddr "127.0.0.1" --rpcapi db,eth,net,web3,personal,admin --cache=1024  --rpcport "8545" --mine --rpccorsdomain "*"  &
```

* Geth process should be executed as background process.

* You can also check the log and mining process by using below command.
```
$ tail -f nohup.out
```
