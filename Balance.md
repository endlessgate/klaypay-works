# Balance
 잔액에 관한 caver-js 사용 방법

## Code Example
### Klay Balance
```javascript
const Caver = require('caver-js')
const caver = new Caver('https://api.baobab.klaytn.net:8651/') // rpc url
// 0x14b5c52f2e37dcd76509e917ffe7043f37d30b19

async function testFunction() {
    // klay get balance
    const hexBalance = await caver.rpc.klay.getBalance('0x14b5c52f2e37dcd76509e917ffe7043f37d30b19')
    
    // bigNumber to string
    const balance = caver.utils.toBN(hexBalance).toString()
    console.log(balance)
}

testFunction()
```

### Token Balance
```javascript
const Caver = require('caver-js')
const caver = new Caver('https://api.baobab.klaytn.net:8651/') // rpc url
// 0x14b5c52f2e37dcd76509e917ffe7043f37d30b19

async function testFunction() {
    // create kip7 instance
    const kip7Instance = caver.kct.kip7.create('0xb74b7f6b977798fd0bfdea0242ddf58540b55429')

    // token get balance
    const balance = await kip7Instance.balanceOf('0x14b5c52f2e37dcd76509e917ffe7043f37d30b19')

    console.log(balance)
}

testFunction()
```

## 속성
이름 | 속성 | 의미
--- | :---: | :---:
`receipt` | https://ko.docs.klaytn.com/dapp/sdk/caver-js/getting-started#checking-receipts | receipt 확인
`에러코드` | https://ko.docs.klaytn.com/dapp/json-rpc/transaction-error-codes | 트랜잭션 에러코드
`참고자료` | https://ko.docs.klaytn.com/dapp/sdk/caver-js/api-references/caver.rpc/klay#caver-rpc-klay-getbalance | caver-js klay.getBalance
`참고자료` | https://ko.docs.klaytn.com/dapp/sdk/caver-js/api-references/caver.kct/kip7#kip7-balanceof | caver-js kip7.balanceOf
`faucet` | https://baobab.wallet.klaytn.com/access?next=faucet | testnet faucet
`baobab` | https://api.baobab.klaytn.net:8651/ | testnet rpc url
`cypress` | https://public-node-api.klaytnapi.com/v1/cypress | mainnet rpc url
