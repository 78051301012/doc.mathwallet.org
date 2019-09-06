# EOS Force DAPP Development Document

## Web dApp Development

### Scatter API

Math Wallet is compatiable with Scatter API.

ScatterJS is really universal that could not only be used with [MathWallet Chrome Extension](https://chrome.google.com/webstore/detail/math-wallet/afbcbjpbpfadlkmhmclhkeeodmamcflc) on desktop but also could be used directly inside mobile terminal such as Math Wallet with just one set of code. By the way, it would be much easier to debug on desktop during development.

#### Scatter API Official Doc

[https://get-scatter.com/docs/setting-up-for-web-apps](https://get-scatter.com/docs/setting-up-for-web-apps)

#### Scatter API Demo Projects

Scatter API Sample developed by MediShares Team

[https://github.com/MediShares/scatter-eos-sample](https://github.com/MediShares/scatter-eos-sample)

Sample project for EOS newbie

[https://github.com/ericfish/EOS-Dev-Book](https://github.com/ericfish/EOS-Dev-Book)

#### dApps using Scatter API

[FINGER GUESS](http://www.guessplay.net)

[Akdex](https://dapp.akdex.io)

#### Scatter API QA

Q. Is it neccessary to distinguish the sactter.js file from wallet or PC side?

A. No, just use 'scatter.min.js'. PC side could run first and then put into Math Wallet and make some mobile adaptation.

Q. How to get more current wallet information, such as orientation / language / fullscreen, etc?

A. We will need math-js-sdk: [https://github.com/mathwallet/math-js-sdk](https://github.com/mathwallet/math-js-sdk)

## Native dApp Development

### SimpleWallet API

If your DAPP is based on native development or browser based, you could open MathWallet to sign your transaction through SimpleWallet protocol or use Math Wallet to scan and authorize.

MathWallet SimpleWallet Protocol supports:

Native APP can open MathWallet to sign your transaction.

This protocol is already used by EOS Knight, Newdex, WhaleEX etc.

To use this API, please read the API doc:

[https://github.com/mathwallet/SimpleWallet](https://github.com/mathwallet/SimpleWallet)

Note: transferReq.blockchain please use 'eosforce'

#### SimpleWallet API Demo Projects

SDK example developed by Math Wallet team:

iOS – [https://github.com/mathwallet/MathWalletSDK-iOS](https://github.com/mathwallet/MathWalletSDK-iOS)

Android – [https://github.com/mathwallet/MathWalletSDK-Android](https://github.com/mathwallet/MathWalletSDK-Android)

## Web dApp Development

Web dApp within mobile browser can open MathWallet to sign your transaction in a link format.

The format is also based on SimpleWallet Protocol MathWallet version:

[https://github.com/mathwallet/SimpleWallet](https://github.com/mathwallet/SimpleWallet)

Demo & Sample Code：

[http://developer.mathwallet.org/sample12/](http://developer.mathwallet.org/sample12/)

[https://github.com/mathwallet/math-eosjs/tree/master/eos/sample12](https://github.com/mathwallet/math-eosjs/tree/master/eos/sample12)

## Scan QRCode API

MathWallet supports scan QRcode to login and sign transaction based on SimpleWallet protocol.

To use this API, please read the API doc:

[https://github.com/mathwallet/SimpleWallet](https://github.com/mathwallet/SimpleWallet)
