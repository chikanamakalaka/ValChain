# <img src="https://raw.githubusercontent.com/chikanamakalaka/valchain/master/V.png" width="300"/>

Valchain is an Ethereum-based blockchain fork from [GoQuorum](https://github.com/ConsenSys/quorum).

Key differences from GoQuorum:

- Re-enable gas price
- Always use Raft consensus
- Change block timestamp unit from nano-second back to second
- Remove block rewards
- Miner receives gas fee from mined transactions
- Hard-coded block difficulty to 1
- Disable private transactions and contracts
- Support p2p for broadcast blocks to public nodes

## Network

![network.png](./docs/network.png)

## Docker

```shell
buildctl build \
    --frontend dockerfile.v0 \
    --local dockerfile=. \
    --local context=. \
    --output type=image,name=${IMAGE},push=true
```

## Install

```shell
git clone https://github.com/Chikanamakalaka/ValChain.git
cd ValChain
make valchain
```

## Run RPC Node

### Mainnet

```shell
valchain --datadir ~/.valchain/mainnet --mainnet --http
```

### Testnet

```shell
valchain --datadir ~/.valchain/testnet --testnet --http
```

## License

The go-ethereum library (i.e. all code outside of the `cmd` directory) is licensed under the
[GNU Lesser General Public License v3.0](https://www.gnu.org/licenses/lgpl-3.0.en.html), also
included in our repository in the `COPYING.LESSER` file.

The go-ethereum binaries (i.e. all code inside of the `cmd` directory) is licensed under the
[GNU General Public License v3.0](https://www.gnu.org/licenses/gpl-3.0.en.html), also included
in our repository in the `COPYING` file.

Any project planning to use the `crypto/secp256k1` sub-module must use the specific [secp256k1 standalone library](https://github.com/ConsenSys/goquorum-crypto-secp256k1) licensed under 3-clause BSD.
