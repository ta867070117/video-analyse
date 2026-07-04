# 短视频去水印解析接口文档

**更新时间：** 2026-07-05  
**接口状态：** 稳定运行  
**联系方式：** 微信 Take5127 / QQ 867070117

---

## 📋 目录

1. [接口概述](#接口概述)
2. [支持平台](#支持平台)
3. [接口地址](#接口地址)
4. [请求参数](#请求参数)
5. [返回参数](#返回参数)
6. [示例代码](#示例代码)
7. [错误码说明](#错误码说明)
8. [注意事项](#注意事项)
9. [联系作者](#联系作者)

---

## 🎯 接口概述

本接口提供主流短视频平台的无水印视频解析服务，支持获取视频原地址、封面图、描述信息等数据。

### 主要功能

- ✅ 解析短视频无水印下载地址
- ✅ 获取视频封面图
- ✅ 获取视频描述信息
- ✅ 支持多平台解析
- ✅ 支持图集内容解析

---

## 🌐 支持平台

### 已支持平台（持续更新中）

| 平台名称 | 状态 | 备注 |
|---------|------|------|
| 抖音 | ✅ 支持 | 包含live图 |
| 快手 | ✅ 支持 | - |
| 西瓜视频 | ✅ 支持 | - |
| 今日头条 | ✅ 支持 | - |
| 小红书 | ✅ 支持 | - |
| 微视 | ✅ 支持 | - |
| 火山小视频 | ✅ 支持 | - |
| TikTok | ✅ 支持 | 国际版抖音 |
| 快手（海外） | ✅ 支持 | - |
| 皮皮虾 | ✅ 支持 | - |
| 小咖秀 | ✅ 支持 | - |
| 趣多拍 | ✅ 支持 | - |
| 美拍 | ✅ 支持 | - |
| 网易云音乐 | ✅ 支持 | 视频内容 |
| 陌陌 | ✅ 支持 | - |
| 映客 | ✅ 支持 | - |
| 阳光宽频 | ✅ 支持 | - |
| 全民K歌 | ✅ 支持 | - |
| 刷宝 | ✅ 支持 | - |
| WIDE短视频 | ✅ 支持 | - |
| YouTube | ✅ 支持 | - |
| 哔哩哔哩 | ✅ 支持 | B站 |
| 最右 | ✅ 支持 | - |
| 皮皮搞笑 | ✅ 支持 | - |
| Vue Blog | ✅ 支持 | - |
| 全民小视频 | ✅ 支持 | - |
| 豆包 | ✅ 支持 | - |
| 视频号 | ✅ 支持 | 微信 |
| 新片场 | ✅ 支持 | - |
| Ins | ✅ 支持 | Instagram |
| 开眼 | ✅ 支持 | - |
| 微博 | ✅ 支持 | - |
| 小影 | ✅ 支持 | - |

> **提示：** 如果需要解析其他平台，请联系作者添加支持

---

## 🔗 接口地址

### 测试接口（GET）

```
https://proxy.layzz.cn/lyz/getAnalyse?token=uuic-qackd-fga-test&link={视频链接}
```

### 正式接口（POST）

```
https://proxy.layzz.cn/lyz/platAnalyse/
```

---

## 📥 请求参数

### POST 请求参数

| 参数名 | 必选 | 类型 | 说明 | 示例 |
|-------|------|------|------|------|
| token | 是 | string | 认证标识 | `uuic-qackd-fga-test` |
| link | 是 | string | 视频连接 | `https://v.douyin.com/iAEnSFyg` |

### 参数说明

- **token**: 接口认证令牌，测试环境使用 `uuic-qackd-fga-test`
- **link**: 视频分享链接，可以直接传入，无需去除中文或其他字符

### Content-Type

```
application/x-www-form-urlencoded
```

> ⚠️ **重要提示：** 必须使用 POST 方式调用，其他方式可能导致参数无法识别

---

## 📤 返回参数

### 返回数据结构

```json
{
  "code": "0001",
  "message": "操作成功",
  "data": {
    "playAddr": "string | null",
    "cover": "string",
    "desc": "string",
    "type": "number",
    "pics": ["string"],
    "music": "string | null",
    "size": "number",
    "videos": ["string"]
  }
}
```

### 字段说明

| 字段名 | 类型 | 说明 |
|-------|------|------|
| code | string | 返回状态码 |
| message | string | 返回消息 |
| data | object | 数据对象 |
| data.playAddr | string/null | 视频播放地址（部分平台） |
| data.cover | string | 视频封面图地址 |
| data.desc | string | 视频描述信息 |
| data.type | number | 内容类型（1=视频，2=图集） |
| data.pics | array | 图集图片列表（type=2时有效） |
| data.music | string/null | 背景音乐地址 |
| data.size | number | 视频大小（字节），-4表示未知 |
| data.videos | array | 视频下载地址列表（动图） |

### 返回示例

#### 示例1：抖音视频

```json
{
  "code": "0001",
  "message": "操作成功",
  "data": {
    "playAddr": null,
    "cover": "https://p11-sign.douyinpic.com/tos-cn-i-0813c000-ce/o0AIwEhA9NVEpAIf5AwuCS1dfTsDACFYnKgEMg~tplv-dy-aweme-images-v2:1440:1920:q80.jpeg?lk3s=138a59ce&x-expires=1776949200&x-signature=g0dVzjZVeV3s%2FkEwbKWI3c8dg60%3D&from=327834062&s=PackSourceEnum_AWEME_DETAIL&se=false&sc=image&biz_tag=aweme_images&l=202603242138109359EDCA683B30923E74",
    "desc": "人设立起来！妹妹钓起来！忧郁装起来！#骗你生儿子 #原相机live #帅哥 #人类幼崽 #抖音",
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

---

## 💻 示例代码

### 1. GET 请求示例（测试用）

```bash
curl "https://proxy.layzz.cn/lyz/getAnalyse?token=uuic-qackd-fga-test&link=https://v.douyin.com/iAEnSFyg"
```

### 2. POST 请求示例（推荐）

#### Python 示例

```python
import requests

url = "https://proxy.layzz.cn/lyz/platAnalyse/"
data = {
    "token": "uuic-qackd-fga-test",
    "link": "https://v.douyin.com/iAEnSFyg"
}

response = requests.post(url, data=data)
result = response.json()

if result["code"] == "0001":
    print("解析成功！")
    print(f"视频地址: {result['data']['videos'][0]}")
    print(f"封面图: {result['data']['cover']}")
    print(f"描述: {result['data']['desc']}")
else:
    print(f"解析失败: {result['message']}")
```

#### JavaScript 示例

```javascript
const axios = require('axios');

const url = 'https://proxy.layzz.cn/lyz/platAnalyse/';
const data = new URLSearchParams({
  token: 'uuic-qackd-fga-test',
  link: 'https://v.douyin.com/iAEnSFyg'
});

axios.post(url, data)
  .then(response => {
    const result = response.data;
    if (result.code === '0001') {
      console.log('解析成功！');
      console.log('视频地址:', result.data.videos[0]);
      console.log('封面图:', result.data.cover);
      console.log('描述:', result.data.desc);
    } else {
      console.log('解析失败:', result.message);
    }
  })
  .catch(error => {
    console.error('请求错误:', error);
  });
```

#### PHP 示例

```php
<?php

$url = 'https://proxy.layzz.cn/lyz/platAnalyse/';
$data = [
    'token' => 'uuic-qackd-fga-test',
    'link' => 'https://v.douyin.com/iAEnSFyg'
];

$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, $url);
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS, http_build_query($data));
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

$response = curl_exec($ch);
curl_close($ch);

$result = json_decode($response, true);

if ($result['code'] == '0001') {
    echo "解析成功！\n";
    echo "视频地址: " . $result['data']['videos'][0] . "\n";
    echo "封面图: " . $result['data']['cover'] . "\n";
    echo "描述: " . $result['data']['desc'] . "\n";
} else {
    echo "解析失败: " . $result['message'] . "\n";
}
```

#### Java 示例

```java
import okhttp3.*;
import org.json.JSONObject;

public class VideoAnalyse {
    public static void main(String[] args) throws Exception {
        OkHttpClient client = new OkHttpClient();
        
        RequestBody formBody = new FormBody.Builder()
                .add("token", "uuic-qackd-fga-test")
                .add("link", "https://v.douyin.com/iAEnSFyg")
                .build();
        
        Request request = new Request.Builder()
                .url("https://proxy.layzz.cn/lyz/platAnalyse/")
                .post(formBody)
                .build();
        
        Response response = client.newCall(request).execute();
        String responseData = response.body().string();
        
        JSONObject json = new JSONObject(responseData);
        if ("0001".equals(json.getString("code"))) {
            JSONObject data = json.getJSONObject("data");
            System.out.println("解析成功！");
            System.out.println("视频地址: " + data.getJSONArray("videos").getString(0));
            System.out.println("封面图: " + data.getString("cover"));
            System.out.println("描述: " + data.getString("desc"));
        } else {
            System.out.println("解析失败: " + json.getString("message"));
        }
    }
}
```

---

## ⚠️ 错误码说明

| 错误码 | 说明 | 解决方案 |
|-------|------|---------|
| 0001 | 操作成功 | - |
| 0000 | 操作失败 | 检查参数是否正确 |
| 1001 | token无效 | 检查token是否正确 |
| 1002 | 链接无效 | 检查视频链接是否正确 |
| 1003 | 不支持的平台 | 该平台暂不支持解析 |
| 1004 | 解析失败 | 视频可能已被删除或私密 |
| 5000 | 服务器错误 | 联系作者 |

> 更多错误码请参考实际返回结果

---

## 📌 注意事项

### 1. 请求方式

- ✅ **必须使用 POST 方式**调用正式接口
- ❌ 不要使用 GET、PUT、DELETE 等其他方式
- ❌ 不要混合使用不同的请求方式

### 2. 链接格式

- 支持短链接（如 `https://v.douyin.com/xxx`）
- 支持完整链接
- **无需手动去除中文或其他字符**，直接传入即可

### 3. Token 使用

- 测试环境使用：`uuic-qackd-fga-test`
- 正式环境需要联系作者获取正式 token

### 4. 视频地址有效期

- 返回的 `videos` 地址通常有 **有效期限制**（几小时到几天不等）
- 建议及时下载，不要长期保存链接

### 5. 图集内容

- 当 `type = 2` 时，表示内容为**图集**
- 图集地址在 `pics` 字段中
- `videos` 字段可能为空或包含封面视频

### 6. 频率限制

- 测试 token 有请求频率限制
- 正式使用请联系作者获取无限制或更高限额的 token

### 7. 法律声明

- 本接口仅供学习交流使用
- 请尊重原创内容，不要用于商业用途
- 下载的内容请在24小时内删除

---

## 📞 联系作者

如有任何问题或需要添加新平台支持，请联系：

- **微信：** Take5127（记得备注"接口解析"）
- **QQ：** 867070117

### 联系时请备注

- 测试接口：备注"接口测试"
- 正式使用：备注"接口解析"
- 添加平台：备注"添加XX平台"

---

## 📝 更新日志

### 2026-07-05

- ✅ 更新文档格式
- ✅ 添加更多平台支持
- ✅ 补充多语言示例代码
- ✅ 完善错误码说明
- ✅ 添加注意事项

### 历史更新

- 初始版本发布
- 支持主流短视频平台解析
- 添加图集内容解析支持

---

## 📄 许可证

本接口版权归作者所有，未经授权不得擅自用于商业用途。

---

**文档结束**

如有问题，请及时联系作者。祝您使用愉快！🎉
