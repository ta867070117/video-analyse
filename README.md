# video-analyse
更新时间【2026-5-8】 短视频去水印接口解析平台支持解析 抖音、快手、巨量、新片场、tiktok 、西瓜视频、今日头条、小红书、微视、  火山小视频、陌陌视频\、映客视频、小咖秀、开眼、全民小视频.全民K歌、最右、小影、微博、美拍、皮皮虾、巨量等平台的短视频去水印解析API接口。 
## 只列举了这么多平台.如果需要其他平台，可以联系作者加
## 短视频去水印解析接口(  请联系作者微信  Take5127   QQ: 867070117)    
## 接口稳定运行，有任何的问题可以跟作者联系哦. 

**接口描述：** 
    
	目前支持的平台 快手、抖音、火山、Ins、今 日头条\、西瓜视频、皮皮虾'\小 咖秀、趣多拍、微视。、美拍、网易云、TikTok、陌陌、映客、阳光宽频、全民K歌、刷宝 、WIDE短视频、小红书、YouTube、哔哩哔哩、最右、皮皮搞笑、vue blog、全民小视频、此处只列举这么多 
	
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
        "playAddr": null,
        "cover": "https://p11-sign.douyinpic.com/tos-cn-i-0813c000-ce/o0AIwEhA9NVEpAIf5AwuCS1dfTsDACFYnKgEMg~tplv-dy-aweme-images-v2:1440:1920:q80.jpeg?lk3s=138a59ce&x-expires=1776949200&x-signature=g0dVzjZVeV3s%2FkEwbKWI3c8dg60%3D&from=327834062&s=PackSourceEnum_AWEME_DETAIL&se=false&sc=image&biz_tag=aweme_images&l=202603242138109359EDCA683B30923E74",
        "desc": "人设立起来！妹妹钓起来！忧郁装起来！#骗你生儿子  #原相机live  #帅哥 #人类幼崽 #抖音",
        "type": 2,
        "pics": [
            "https://p11-sign.douyinpic.com/tos-cn-i-0813c000-ce/o0AIwEhA9NVEpAIf5AwuCS1dfTsDACFYnKgEMg~tplv-dy-aweme-images-v2:1440:1920:q80.jpeg?lk3s=138a59ce&x-expires=1776949200&x-signature=g0dVzjZVeV3s%2FkEwbKWI3c8dg60%3D&from=327834062&s=PackSourceEnum_AWEME_DETAIL&se=false&sc=image&biz_tag=aweme_images&l=202603242138109359EDCA683B30923E74",
            "https://p11-sign.douyinpic.com/tos-cn-i-0813c000-ce/oIAASIAY5hpAx9jIf2EICFuA9E1DKwNnVEfCgT~tplv-dy-aweme-images-v2:1440:1920:q80.jpeg?lk3s=138a59ce&x-expires=1776949200&x-signature=U6pnR9adCIHXrGEK%2B%2B1ufWPp9Us%3D&from=327834062&s=PackSourceEnum_AWEME_DETAIL&se=false&sc=image&biz_tag=aweme_images&l=202603242138109359EDCA683B30923E74",
            "https://p3-sign.douyinpic.com/tos-cn-i-0813c000-ce/oInDyAWAECbAI1FwpjTAVISfKNh9CYAu5EEzfg~tplv-dy-aweme-images-v2:1440:1920:q80.jpeg?lk3s=138a59ce&x-expires=1776949200&x-signature=25LT0adAf2jsIUB2%2FkJ8XQa8F0o%3D&from=327834062&s=PackSourceEnum_AWEME_DETAIL&se=false&sc=image&biz_tag=aweme_images&l=202603242138109359EDCA683B30923E74"
        ],
        "music": null,
        "size": -4,
        "videos": [
            "https://v5-coldm.douyinvod.com/507d62edd445208fd465d6c44c44e141/69c2a1d4/video/tos/cn/tos-cn-ve-15c000-ce/osLKeOBTcA8yJf5FIahkN7RDOvyeIZ73BPggQG/?a=1128&ch=26&cr=13&dr=0&lr=all&cd=0%7C0%7C0%7C&br=892&bt=892&cs=0&ds=3&ft=8ILtMUUmf.7daD0PD1YBaUA-fmGs9fK..-XnRkaJ0XURejVhWJ6&mime_type=video_mp4&qs=0&rc=O2UzNjY5Ojg8PDM3MztoNEBpM2l1eHA5cnFsOTMzbGkzNUA0Ly1jNmBgNjMxLl8wYC1iYSNsbTBlMmQ0L3BhLS1kLTRzcw%3D%3D&btag=c0010e0008d008&cdn_type=1&cquery=100b&dy_q=1774359491&feature_id=f5241e7604dff1d9d6c943fd20bd51a2&l=202603242138109359EDCA683B30923E74&n80=1&n80_dm=bjk4LXYtbmNkbmFiMy5kb3V5aW52b2QuY29t&n80_tk=45602b0f9ef4525b37ea5110f61069b6&pdp=online_xy&pwid=280&req_cdn_type=r",
            "https://v11-cold.douyinvod.com/8d77d6e844323611a1c76bb4b59664d4/69c2a1d5/video/tos/cn/tos-cn-ve-15c000-ce/o8IGTcHcEgvkBDMWhwaJtpyAINOeyfQQSgeL7R/?a=1128&ch=26&cr=13&dr=0&lr=all&cd=0%7C0%7C0%7C&br=671&bt=671&cs=0&ds=3&ft=8ILtMUUmf.7daD0PD1YBaUA-fmGs9fK..-XnRkaJ0XURejVhWJ6&mime_type=video_mp4&qs=0&rc=ZzVnOjc4Nzg5aWk1Zmc6ZEBpM3kzc3E5cm9sOTMzbGkzNUBhMzJgYTAxNTUxMDNiYjYuYSNnaDIvMmRzM3BhLS1kLTRzcw%3D%3D&btag=c0010e0008d008&cdn_type=7&cquery=100b&dy_q=1774359491&feature_id=f5241e7604dff1d9d6c943fd20bd51a2&l=202603242138109359EDCA683B30923E74&n80=1&n80_dm=bjk4LXYtbmNkbmFiMy5kb3V5aW52b2QuY29t&n80_tk=b27160675533da57c17b13128ff1843d&pwid=280&req_cdn_type=r"
        ]
    }
}
```
