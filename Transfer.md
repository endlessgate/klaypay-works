# Transfer 
 전송에 관한 caver-js 사용 방법

## Code Example
### Klay 전송
``` javascript
const Caver = require('caver-js')
const caver = new Caver('https://api.baobab.klaytn.net:8651/') // rpc url
// 0x79ae25dc7d5b21bd00a731c83fcb27e78f21483d8d20e979f4b49921573e08a5

async function testFunction() {
    const keyring = caver.wallet.keyring.createFromPrivateKey('0x79ae25dc7d5b21bd00a731c83fcb27e78f21483d8d20e979f4b49921573e08a5')
    caver.wallet.add(keyring)
    
    // make transaction
    const valueTransferTransaction = caver.transaction.valueTransfer.create({
        from: keyring.address,
        to: "0x79912164b5e3b1d16ebd831767b4244445a41747",
        value: 1,
        gas: 30000,
    })
    
    // sign transaction
    await caver.wallet.sign(keyring.address, valueTransferTransaction)
    
    // encode transaction
    const encodedTransaction = valueTransferTransaction.getRLPEncoding()
    console.log(`RLP-encoded: ${encodedTransaction}`)

    // send trasaction
    const receipt = await caver.rpc.klay.sendRawTransaction(encodedTransaction)
    console.log(receipt)
}

testFunction()
```

### Token 전송
```javascript
const Caver = require('caver-js')
const caver = new Caver('https://api.baobab.klaytn.net:8651/') // rpc url
// 0x79ae25dc7d5b21bd00a731c83fcb27e78f21483d8d20e979f4b49921573e08a5

async function testFunction() {
    // wallet add
    const keyring = caver.wallet.keyring.createFromPrivateKey('0x79ae25dc7d5b21bd00a731c83fcb27e78f21483d8d20e979f4b49921573e08a5')
    caver.wallet.add(keyring)
    
    // create kip7 instance
    // caver.kct.kip7.create([tokenAddress])
    const kip7Instance = caver.kct.kip7.create('0xb74b7f6b977798fd0bfdea0242ddf58540b55429')
    
    // token transfer
    // kip7.transfer(recipient, amount [, sendParam])
    const receipt = await kip7Instance.transfer('0x79912164B5E3B1d16EbD831767b4244445a41747', 1, { from: '0x14b5c52f2e37dcd76509e917ffe7043f37d30b19'})
    console.log(receipt)
}

testFunction()
```

## 속성
이름 | 속성 | 의미
--- | :---: | :---:
`에러코드` | https://ko.docs.klaytn.com/dapp/json-rpc/transaction-error-codes | 트랜잭션 에러코드
`receipt` | [check-receipts](https://ko.docs.klaytn.com/dapp/sdk/caver-js/getting-started#checking-receipts) | caver-js
`참고자료` | [kip7.transfer](https://ko.docs.klaytn.com/dapp/sdk/caver-js/api-references/caver.kct/kip7#kip7-transfer) | caver-js
`faucet` | https://baobab.wallet.klaytn.com/access?next=faucet | testnet faucet
`baobab` | https://api.baobab.klaytn.net:8651/ | testnet rpc url
`cypress` | https://public-node-api.klaytnapi.com/v1/cypress | mainnet rpc url
