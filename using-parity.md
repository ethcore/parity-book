# Using Parity

Assuming you installed Parity, you can start the client with a simple `parity`. By default it will connect to other nodes on the Ethereum Homestead network and synchronise the blockchain. You can instead connect to the Morden testnet by using the CLI parameter `--chain=testnet`.

Use `parity --help` to get help on other options.

## JSON-RPC API

You can do most of the examples on [Ethereum's JSON-RPC](https://github.com/ethcore/parity/wiki/JSONRPC) with Parity. e.g.:

````
> curl -X POST -H "Content-Type: application/json" --data '{"jsonrpc":"2.0","method":"eth_getBalance","params":["0x0037a6b811ffeb6e072da21179d11b1406371c63", "latest"],"id":1}' http://127.0.0.1:8545
{"jsonrpc":"2.0","result":"0x0406c5a45045137507eb","id":1}
````

{% hint style='info' %}
Unlike older Ethereum clients, Parity requires a `Content-Type` of `application/json`. When using `curl` ensure that the appropriate `-H` argument is provided (like the example above).
{% endhint %}

## Javascript Console

Ethereum has the [web3 Javascript API](https://github.com/ethereum/wiki/wiki/JavaScript-API) for interacting with an Ethereum client.

### Node.js CLI Console

Parity doesn't include a Javascript interpreter but if you want to use an interactive Jaavscript console, you can install [node/NPM](http://nodejs.org) and use its console. Once you have node/NPM installed, you'll just need to install the latest web3 module:

```bash
$ npm install web3
```

From then on you just need to run `node` and require the web3 module:

```bash
$ node
> Web3 = require("web3")
> web3 = new Web3(new Web3.providers.HttpProvider("http://localhost:8545"));
```

After this point, you'll be able to use the web3 API from with this environment, e.g.:

```javascript
> web3.eth.blockNumber
743397
```

### Chrome Browser Console

You can also use the Google Chrome console for web3 development. Head to [http://localhost:8080/](http://localhost:8080/) and you'll be able to use Chrome's builtin console right away for web3 development.
