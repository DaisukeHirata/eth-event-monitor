# EthereumCasts

## eth subscribe

https://infura.io/docs/wss/eth_subscribe

```
wscat -c wss://rinkeby.infura.io/ws
```

```
{"id": 1, "method": "eth_subscribe", "params": ["logs", {"address": ["0x974f51997d09c702475fc2cf8dbdb12d17b10ddc"]}]}
```

## eth_getTransactionByHash

https://infura.io/docs/api/get/eth_getTransactionByHash

```
curl -G https://api.infura.io/v1/jsonrpc/rinkeby/eth_getTransactionByHash --data-urlencode 'params=["0x1393ebee5829c704fc83ec2d27755e4d93d03f499a2343ab2f980c83b5e5ac65"]' | jq
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   720  100   720    0     0    883      0 --:--:-- --:--:-- --:--:--   882
{
  "jsonrpc": "2.0",
  "id": 0,
  "result": {
    "blockHash": "0x0f07a673eda4e112d6544988641289678655259e179e6247df9c1baa4643f1b3",
    "blockNumber": "0x2e2abf",
    "from": "0xf157036c6568fba59d085024c67165c7c788d466",
    "gas": "0x657a2f",
    "gasPrice": "0x3b9aca00",
    "hash": "0x1393ebee5829c704fc83ec2d27755e4d93d03f499a2343ab2f980c83b5e5ac65",
    "input": "0xa9059cbb000000000000000000000000c234e6acc0f3f8eee1b19f4032e92971a61945da0000000000000000000000000000000000000000000000000000000ba43b7400",
    "nonce": "0xd8",
    "r": "0x55739994073d22600f48f6009ff6fb1cac884e56fa252373007dc070d88bc50a",
    "s": "0x48601449676c95d648c1fc209f4cbb60f4a868759020d678be4a976e9adce0ad",
    "to": "0x974f51997d09c702475fc2cf8dbdb12d17b10ddc",
    "transactionIndex": "0x5",
    "v": "0x2b",
    "value": "0x0"
  }
}
```

### run decode

place `input` from eth_getTransactionByHash to testData

```
node index.js
```

```json
{ name: 'transfer',
  params: 
   [ { name: '_to',
       value: '0xc234e6acc0f3f8eee1b19f4032e92971a61945da',
       type: 'address' },
     { name: '_value', value: '50000000000', type: 'uint256' } ] }
```