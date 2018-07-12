[视频演示](http://yxshare.oss-cn-hangzhou.aliyuncs.com/douyin/http%E6%9C%AC%E5%9C%B0%E6%9C%8D%E5%8A%A1%E5%99%A8%E6%96%B9%E5%BC%8F%E8%8E%B7%E5%8F%96%E6%95%B0%E6%8D%AE.mp4)

> 如果您不懂go代码或者无心研究算法本身，可以通过在服务器或PC上运行本程序，并通过简单的本地http请求方式访问抖音数据

+ 可以查阅[抖音签名算法GO语言版](https://github.com/sweet8-asia/douyin-sign)，来研究抖音算法本身。
+ [本程序也可以直接通过命令行获取数据](https://github.com/sweet8-asia/douyin-demo/blob/master/%E9%80%9A%E8%BF%87%E5%91%BD%E4%BB%A4%E8%A1%8C%E6%96%B9%E5%BC%8F%E8%B0%83%E7%94%A8.md)

> 以下是抖音本地http服务的演示说明，需要程序的可加QQ:2811481636

> 首先需要要在本地运行http服务器，端口为9102

`douyin-demo http`


>接口分为无需登录和登录两部分


## 无需登录接口演示：
+ [无需登录]获取首页动态列表：

[http://127.0.0.1:9102/api?action=feed&type=0&count=100&max_cursor=0&min_cursor=0](http://127.0.0.1:9102/api?action=feed&type=0&count=100&max_cursor=0&min_cursor=0)

+ [无需登录]搜索用户：

[http://127.0.0.1:9102/api?action=discover/search&keyword=美女&type=1&cursor=0&count=10](http://127.0.0.1:9102/api?action=discover/search&keyword=美女&type=1&cursor=0&count=10)

+ [无需登录]获取作品列表：

[http://127.0.0.1:9102/api?action=aweme/post&user_id=83774364341&max_cursor=0&count=200](http://127.0.0.1:9102/api?action=aweme/post&user_id=83774364341&max_cursor=0&count=200)

+ [无需登录]获取用户信息：

[http://127.0.0.1:9102/api?action=user&user_id=83774364341](http://127.0.0.1:9102/api?action=user&user_id=83774364341)

+ [无需登录]获取用户关注列表：

[http://127.0.0.1:9102/api?action=user/follower/list&user_id=83774364341&count=20&max_time=1531394616](http://127.0.0.1:9102/api?action=user/follower/list&user_id=83774364341&count=20&max_time=1531394616)

+ [无需登录]获取用户粉丝列表：

[http://127.0.0.1:9102/api?action=user/following/list&user_id=83774364341&count=20&max_time=1531394616](http://127.0.0.1:9102/api?action=user/following/list&user_id=83774364341&count=20&max_time=1531394616)

+ [无需登录]获取用户喜欢的作品列表：

[http://127.0.0.1:9102/api?action=aweme/favorite&user_id=83774364341&count=20&max_time=1531394616](http://127.0.0.1:9102/api?action=aweme/favorite&user_id=83774364341&count=20&max_time=1531394616)

+ [无需登录]获取附近的feed列表：

[http://127.0.0.1:9102/api?action=nearby/feed&type=0&count=100&max_cursor=0&min_cursor=0](http://127.0.0.1:9102/api?action=nearby/feed&type=0&count=100&max_cursor=0&min_cursor=0)


+ [无需登录]播放 

[http://127.0.0.1:9102/api?action=play&video_id=v0200f150000bcjhd5jbo1i96tqjqp90&line=0&ratio=720p](http://127.0.0.1:9102/api?action=play&video_id=v0200f150000bcjhd5jbo1i96tqjqp90&line=0&ratio=720p)

## 如何使用账号密码登录：

+ 生成设备信息

[http://127.0.0.1:9102/device](http://127.0.0.1:9102/device)

+ 不填充验证码(手机号码前缀+86一定要转义为%2B86)，如果需要验证码，会返回验证码图片

[http://127.0.0.1:9102/login?mobile=%2B17702032055&password=poilkjmnb123&device_id=50311297598&iid=37764280446&uuid=866265035315870&openudid=4617150637217100&captcha=](http://127.0.0.1:9102/login?mobile=%2B17702032055&password=poilkjmnb123&device_id=50311297598&iid=37764280446&uuid=866265035315870&openudid=4617150637217100&captcha=)

+ 如果上述结果需要验证码，则填充验证码，后再请求

[http://127.0.0.1:9102/login?mobile=%2B17702032055&password=poilkjmnb123&device_id=50311297598&iid=37764280446&uuid=866265035315870&openudid=4617150637217100&captcha=p8ux](http://127.0.0.1:9102/login?mobile=%2B17702032055&password=poilkjmnb123&device_id=50311297598&iid=37764280446&uuid=866265035315870&openudid=4617150637217100&captcha=p8ux)


## 需要登录的接口演示（传递登录返回的user_id到uid参数）：

+ [需登录]喜欢 

[http://127.0.0.1:9102/api?uid=96183592775&action=commit/item/digg&aweme_id=6577254073496505604&type=1](http://127.0.0.1:9102/api?user_id=96183592775&action=commit/item/digg&aweme_id=6577254073496505604&type=1)

+ [需登录]关注 

[http://127.0.0.1:9102/api?uid=96183592775&action=commit/follow/user&user_id=65146937437](http://127.0.0.1:9102/api?user_id=96183592775&action=commit/follow/user&user_id=65146937437)

+ [需登录]评论 
[http://127.0.0.1:9102/api?uid=96183592775&action=comment/publish&aweme_id=6577254073496505604&text=很不错哦](http://127.0.0.1:9102/api?user_id=96183592775&action=comment/publish&aweme_id=6577254073496505604&text=很不错哦)

