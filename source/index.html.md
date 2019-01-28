---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://github.com/spadebuilders/ethereum-json-rpc-spec/blob/master/ethereum-json-rpc-1474.md'>ethereum-json-rpc-1474</a>

includes:
  - errors

search: true
---

# Introduction

Nodes created by the current generation of Ethereum clients expose inconsistent and incompatible remote procedure call (RPC) methods because no formal Ethereum RPC specification exists. This proposal standardizes such a specification to provide developers with a predictable Ethereum RPC interface regardless of underlying node implementation.

# Ethereum JSON RPC

## web3_clientVersion

```shell
curl -X POST --header "Content-Type: application/json" --data '{"jsonrpc":"2.0","method":"web3_clientVersion","params":[],"id":67}' http://localhost:8545
```

> The above command returns JSON structured like this:

```json
{"jsonrpc":"2.0","id":67,"result":"Geth/v1.8.21-stable/linux-amd64/go1.11.4"}
```

Returns the version of the current client

## web3_sha3

```shell
curl -X POST --header "Content-Type: application/json" --data '{"jsonrpc":"2.0","method":"web3_sha3","params":["0x68656c6c6f20776f726c64"],"id":64}' http://localhost:8545
```

> The above command returns JSON structured like this:

```json
{"jsonrpc":"2.0","id":64,"result":"0x47173285a8d7341e5e972fc677286384f802f8ef42a5ec5f03bbfa254cb01fad"} 
```

Hashes data using the Keccak-256 algorithm

### Parameters

DATA - the data to convert into a SHA3 hash.
```
params: [
  "0x68656c6c6f20776f726c64"
]
```

### Returns

DATA - The SHA3 result of the given string.

## net_listening

```shell
curl -X POST --header "Content-Type: application/json" --data '{"id": 1337,"jsonrpc": "2.0","method": "net_listening","params": []}' http://localhost:75
45
```

> The above command returns JSON structured like this:

```json
{"jsonrpc":"2.0","id":1337,"result":true}
```

Determines if this client is listening for new network connections

### Parameters

_(none)_

### Returns

{`boolean`} - `true` if listening is active or `false` if listening is not active

## net_peerCount

```shell
curl -X POST --header "Content-Type: application/json" --data '{"id": 1337,"jsonrpc": "2.0","method": "net_peerCount","params": []}' http://localhost:7545
```
> The above command returns JSON structured like this:

```json
{"jsonrpc":"2.0","id":1337,"result":"0x19"}
```
Returns the number of peers currently connected to this client


### Parameters
_(none)_

### Returns

{`Quantity`} - number of connected peers

## net_version

```shell
curl -X POST --header "Content-Type: application/json" --data '{"id": 1337, "jsonrpc": "2.0","method": "net_version","params": []}' http://localhost:8545
```
> The above command returns JSON structured like this:

```json
{"jsonrpc":"2.0","id":1337,"result":"1"}
```

Returns the chain ID associated with the current network

### Parameters
_(none)_

### Returns

{`string`} - chain ID associated with the current network

Common chain IDs:

* "1" - Ethereum mainnet
* "3" - Ropsten testnet
* "4" - Rinkeby testnet
* "42" - Kovan testnet

Note: See EIP-155 for a [complete list](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-155.md#list-of-chain-ids) of possible chain IDs.

## eth_accounts

```shell
curl -X POST --header "Content-Type: application/json" --data '{"id": 1337,"jsonrpc": "2.0","method": "eth_accounts","params": []}' http://localhost:8545
```
> The above command returns JSON structured like this:

```json
{
    "id": 1337,
    "jsonrpc": "2.0",
    "result": ["0xc94770007dda54cF92009BFF0dE90c06F603a09f"]
}
```
### Parameters
_(none)_

### Returns
{`Data[]`} - array of addresses




