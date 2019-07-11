# Shared_Preferences文件敏感信息保护
## 测试描述
App在处理运行时产生的敏感数据（如账号、密码、手机号、Cookie、Token等业务相关敏感信息）时，将未经加密的敏感信息以明文的形式保存在文件或者本地数据库中。
## 风险危害
当用户手机失窃或者连接到电脑等情况时，这些明文的敏感数据可能被第三方程序获取，导致用户的账号、密码、手势密码、手机号等个人敏感信息容易泄露。
## 测试步骤
1、登录目标APP，先尽可能多的完善个人信息。
2、使用adb工具查看[/data/data/package-name/shared_prefs/]目录下的文件，查找其中是否包含敏感信息，如下图：
![images-text](https://github.com/aoe-xiaoyue/wz/blob/master/images/1222.png)
## 修复建议
1、对敏感信息进行加密保护。  
2、根据业务需求确定必需在本地存储的数据，不必要的数据不存储。
## 参考链接
* [Android数据存储之SharedPreferences及如何安全存储](https://www.cnblogs.com/whoislcj/p/5494761.html)
* [Android本地数据存储：Shared Preferences安全风险浅析](http://www.tuicool.com/articles/rqyE3q)
* [Android 密钥库系统](https://developer.android.com/training/articles/keystore.html)
