# 更多问题

### Q 怎么判断是否通过麦子dapp浏览器打开的链接？

useragent 里面如果有 MdsApp，表示是麦子钱包的浏览器访问

### Q: 如何在 DAPP 页面获取钱包信息、全屏、打开微信、横屏、当前语言等信息和操作？

可以通过 math-js-sdk: [https://github.com/mathwallet/math-js-sdk](https://github.com/mathwallet/math-js-sdk)

### Q: 如何在麦子钱包中调试 DAPP？

麦子钱包提供DAPP浏览器和手机端调试工具，具体调试方法查看：[http://blog.mathwallet.net/?p=1248](http://blog.mathwallet.net/?p=1248)

### Q: 如何在麦子钱包是否支持测试链？

不支持，我们建议您在桌面端完成测试环境的测试，这样效率更高一些。

### Q：如何让 DAPP 在麦子钱包中【横屏】打开？

有两种方法：

1 由麦子钱包配置该 DAPP 横屏打开，只需要联系麦子钱包团队即可

2 在 DAPP 页面上调用 math-js-sdk: [https://github.com/mathwallet/math-js-sdk](https://github.com/mathwallet/math-js-sdk) 的 orientation 方法

### Q: 如何让 DAPP 在麦子钱包中【全屏】打开？

在 DAPP 页面上调用 math-js-sdk: [https://github.com/mathwallet/math-js-sdk](https://github.com/mathwallet/math-js-sdk) 的 fullScreen(1) 方法。
同时建议您在 DAPP 上加入退出全屏或退出按钮，并调用 math-js-sdk 的 fullScreen(0) 和 close() 方法。

### Q: 如何通过钱包接口获取用户手机的 Device ID？

在 DAPP 页面上调用 math-js-sdk: [https://github.com/mathwallet/math-js-sdk](https://github.com/mathwallet/math-js-sdk) 的 getAppInfo() 方法，在返回值中获取 deviceId 即可。

### Q: DAPP 怎样获取钱包DAPP浏览器语言？

示例代码如下：

```
/**
 * 获取浏览器语言类型
 * @return {string} 浏览器国家语言
 */
var getNavLanguage = function(){
  navLanguage = (navigator.language || navigator.browserLanguage ).toLowerCase();
  switch(navLanguage)
  {
  case 'zh-cn' || 'zh-tw' || 'zh-hk':
    navLanguage = 'cn';
    break;
  case 'ko':
    navLanguage = 'ko'
    break;
  default:
    navLanguage = 'en';
  }
  return navLanguage;
}
```

### Q: 如何通过网页打开麦子钱包，并跳转到 DAPP 页面？

你可以使用 Deeplink，示例URL代码如下，修改 dappUrl 为你希望跳转的地址即可：

```
mathwallet://mathwallet.org?param={"action":"openUrl","protocol":"SimpleWallet","dappUrl":"https:\/\/gateway.eosdt.com\/","dappName":"MathWalletSDK-Demos","blockchain":"eosio","version":"1.0","callback":"appABC:\/\/abc.com?action=openUrl","desc":"","dappIcon":""}
```

目前 Deeplink 仅支持 Ethereum、EOS、EOS Force、TRON

callback 会在支付成功后跳转并带上相应参数，例如：
appABC://abc.com?action=openUrl&result=1

result 的返回值：0 cancel, 1 success, 2 fail

如果有交易，则会加上 txID
appABC://abc.com?action=openUrl&transfer=1&txID=xxx