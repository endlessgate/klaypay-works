# History
 receipts에 관한 caver-js 사용 방법

## Code Example
### GetTransaction
```javascript
const Caver = require('caver-js')
const caver = new Caver('https://api.baobab.klaytn.net:8651/') // rpc url
// 0x14b5c52f2e37dcd76509e917ffe7043f37d30b19

async function testFunction() {
    // get transaction
    const transaction = await caver.rpc.klay.getTransactionByHash('0x8ca95dc5add9a7f1d67ccec13fdeae32a38b84b366c2ea5bf83bba100bf16fd2')

    console.log(transaction)
}

testFunction()
```


### GetTransactionReceipt
```javascript
const Caver = require('caver-js')
const caver = new Caver('https://api.baobab.klaytn.net:8651/') // rpc url
// 0x14b5c52f2e37dcd76509e917ffe7043f37d30b19

async function testFunction() {
    // get transaction receipts
    const receipt = await caver.rpc.klay.getTransactionReceipt('0x8ca95dc5add9a7f1d67ccec13fdeae32a38b84b366c2ea5bf83bba100bf16fd2')

    console.log(receipt)
}

testFunction()
```

## 속성
이름 | 속성 | 의미
--- | :---: | :---:
`에러코드` | https://ko.docs.klaytn.com/dapp/json-rpc/transaction-error-codes | 트랜잭션 에러코드
`receipt` | [check-receipts](https://ko.docs.klaytn.com/dapp/sdk/caver-js/getting-started#checking-receipts) | caver-js
`참고자료` | [GetTransaction](https://ko.docs.klaytn.com/dapp/sdk/caver-js/api-references/caver.rpc/klay#caver-rpc-klay-gettransactionbyhash) | caver-js
`참고자료` | [GetTransactionReceipt](https://ko.docs.klaytn.com/dapp/sdk/caver-js/api-references/caver.rpc/klay#caver-rpc-klay-gettransactionreceipt) | caver-js
`faucet` | https://baobab.wallet.klaytn.com/access?next=faucet | testnet faucet
`baobab` | https://api.baobab.klaytn.net:8651/ | testnet rpc url
`cypress` | https://public-node-api.klaytnapi.com/v1/cypress | mainnet rpc url
