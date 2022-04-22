# 지갑 생성

## Code Example
``` javascript
const Caver = require('caver-js')
const caver = new Caver('https://api.baobab.klaytn.net:8651/')

async function testFunction() {
    const keyring = caver.wallet.keyring.generate()
    console.log(keyring)
}
testFunction()
```
## 속성
이름 | 의미 | 설명
--- | :---: | :---:
`privateKey` | privateKey 가져오는 방식 | keyring.privateKey
