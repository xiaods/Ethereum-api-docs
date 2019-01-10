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
curl -X POST --data '{
    "id": 1337,
    "jsonrpc": "2.0",
    "method": "web3_clientVersion",
    "params": [],
}' http://localhost:8545
```

> The above command returns JSON structured like this:

```json
{
    "id": 1337,
    "jsonrpc": "2.0",
    "result": "Mist/v0.9.3/darwin/go1.4.1"
}
```

Returns the version of the current client

## web3_sha3

```shell
curl -X POST --data '{
    "id": 1337,
    "jsonrpc": "2.0",
    "method": "web3_sha3",
    "params": ["0x68656c6c6f20776f726c64"]
}' http://localhost:8545
```

> The above command returns JSON structured like this:

```json
{
    "id": 1337,
    "jsonrpc": "2.0",
    "result": "0xc94770007dda54cF92009BFF0dE90c06F603a09f"
}
```

Hashes data using the Keccak-256 algorithm

### Parameters

|#|Type|Description|
|-|-|-|
|1|{[`Data`](#data)}|data to hash|

### Returns

{[`Data`](#data)} - Keccak-256 hash of the given data

## net_listening

```shell
curl -X POST --data '{
    "id": 1337,
    "jsonrpc": "2.0",
    "method": "net_listening",
    "params": []
}' http://localhost:8545
```

> The above command returns JSON structured like this:

```json
{
    "id": 1337,
    "jsonrpc": "2.0",
    "result": true
}
```

Determines if this client is listening for new network connections

### Parameters

_(none)_

### Returns

{`boolean`} - `true` if listening is active or `false` if listening is not active

