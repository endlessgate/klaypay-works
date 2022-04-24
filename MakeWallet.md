# 지갑 생성
지갑 생성에 관한 caver-js 사용 방법

## Code Example
``` javascript
const Caver = require('caver-js')
const caver = new Caver('https://api.baobab.klaytn.net:8651/') // rpc url

async function testFunction() {
    const keyring = caver.wallet.keyring.generate()
    console.log(keyring)
}
testFunction()
```
## 속성
이름 | 속성 | 의미
--- | :---: | :---:
`privateKey` | keyring.privateKey | privateKey 가져오는 방법
`address` | keyring.address | address 가져오는 방법
`참고자료` | [keyring API Reference](https://ko.docs.klaytn.com/dapp/sdk/caver-js/api-references/caver.wallet/keyring) | caver-js
`참고자료` | https://ko.docs.klaytn.com/dapp/sdk/caver-js/getting-started#adding-keyrings-to-caver-js | 인메모리 지갑에 keyring추가
`baobab` | https://api.baobab.klaytn.net:8651/ | testnet rpc url
`cypress` | https://public-node-api.klaytnapi.com/v1/cypress | mainnet rpc url
