# Errors

<aside class="notice">
If an Ethereum RPC method encounters an error, the error member included on the response object MUST be an object containing a code member and descriptive message member. The following list contains all possible error codes and associated messages:
</aside>

|Code|Message|Meaning|Category|
|-|-|-|-|
|-32700|Parse error|Invalid JSON|standard|
|-32600|Invalid request|JSON is not a valid request object|standard|
|-32601|Method not found|Method does not exist|standard|
|-32602|Invalid params|Invalid method parameters|standard|
|-32603|Internal error|Internal JSON-RPC error|standard|
|-32000|Invalid input|Missing or invalid parameters|non-standard|
|-32001|Resource not found|Requested resource not found|non-standard|
|-32002|Resource unavailable|Requested resource not available|non-standard|
|-32003|Transaction rejected|Transaction creation failed|non-standard|
|-32004|Method not supported|Method is not implemented|non-standard|


## Example error response:

```json
{
    "id": 1337
    "jsonrpc": "2.0",
    "error": {
        "code": -32003,
        "message": "Transaction rejected"
    }
}
```
