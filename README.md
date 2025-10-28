# video-analyse
更新时间【2025-10-28】 短视频去水印接口解析平台支持解析 抖音、快手、巨量、新片场、tiktok 、西瓜视频、今日头条、小红书、微视、  火山小视频、陌陌视频\、映客视频、小咖秀、开眼、全民小视频.全民K歌、最右、小影、微博、美拍、皮皮虾、巨量等平台的短视频去水印解析API接口。 
## 只列举了这么多平台.如果需要其他平台，可以联系作者加
## 短视频去水印解析接口(  请联系作者微信  Take5127   QQ: 867070117)    
## 接口稳定运行，有任何的问题可以跟作者联系哦. 

**接口描述：** 
    
	目前支持的平台 快手、抖音、火山、FaceBook、Ins、今 日头条\、西瓜视频、皮皮虾'\小 咖秀、趣多拍、微视。、美拍、网易云、TikTok、陌陌、映客、阳光宽频、全民K歌、刷宝 、WIDE短视频、小红书、YouTube、哔哩哔哩、最右、皮皮搞笑、vue blog、全民小视频、此处只列举这么多 
	
	有任何疑问请联系作者微信    Take5127  记得备注接口解析  。

**测试请求URL：** 

https://proxy.layzz.cn/lyz/getAnalyse?token=uuic-qackd-fga-test&link=https://v.douyin.com/iAEnSFyg

**POST请求URL：**
- ` https://proxy.layzz.cn/lyz/platAnalyse/`
  
**请求方式：**
- POST 

-   默认post方式调用
-   如果以其他方式调用，可能会产生无法识别参数，调用不成功等情况

### POSTMAN 请求调用示例

![](https://parse-video-server.oss-cn-hangzhou.aliyuncs.com/oneblog/20190808154118077.png)

**参数：** 

|参数名|必选|类型|说明|
|:---- |:---|:----- |-----   |
|token |是  |string |认证标识 测试请用此token   uuic-qackd-fga-test   |
|link |是  |string | 视频连接 可以直接丢过来，不用去除中文   |

 **返回示例**

```
  {
    "code": "0001",
    "message": "操作成功",
    "data": {
        "playAddr": "http://txmov2.a.yximgs.com/upic/2019/08/08/06/BMjAxOTA4MDgwNjQ2NTZfMTQwMDczNjc1M18xNjEzODkyNDI2MF8xXzM=_b_B74123b4bd6568a1077016bcefc18abe1.mp4?tag=1-1565249965-sp-0-qof1r1hxsh-cb47e930d97d4584&type=hot",
        "cover": "http://tx2.a.yximgs.com/upic/2019/08/08/06/BMjAxOTA4MDgwNjQ2NTZfMTQwMDczNjc1M18xNjEzODkyNDI2MF8xXzM=_B46c1b12705878ed351c785f5193d39b8.jpg?tag=1-1565249965-sp-0-pg8ag4xvhg-2ab68b6f6faf1885&type=hot",
        "desc": "孙俪工作室"
    }
}
```
