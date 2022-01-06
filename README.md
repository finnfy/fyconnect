# 飛宇互联

> 支付宝、QQ、微博、百度

## 1.授权登录
**请求地址**：
http://connect.0fy0.com/oauth2.0/authorize

**请求方法**：
GET

**请求参数**：
请求参数请包含如下内容：


|     参数      | 是否必须 |                             含义                             |
| :-----------: | :------: | :----------------------------------------------------------: |
| appid |   必须   |                 应用的appid                 |
|   redirect_uri   |   必须   |            成功授权后的回调地址，必须是注册appid时填写的主域名下的地址             |
| type  |   必须   | 登录方式。"qq"或"alipay"或"sina"或"baidu" |

**示例**

> http://connect.0fy0.com/oauth2.0/authorize?appid=2022201018&redirect_uri=https://0fy0.com/return.php&type=qq
>
> http://connect.0fy0.com/oauth2.0/authorize?appid=2022201018&redirect_uri=https://0fy0.com/return.php&type=alipay
>
> http://connect.0fy0.com/oauth2.0/authorize?appid=2022201018&redirect_uri=https://0fy0.com/return.php&type=sina
>
> http://connect.0fy0.com/oauth2.0/authorize?appid=2022201018&redirect_uri=https://0fy0.com/return.php&type=baidu



## 2.获取用户信息
**请求地址**：
http://connect.0fy0.com/oauth2.0/get_user_info

**请求方法**：
GET/POST

**请求参数**：
请求参数请包含如下内容：


|     参数      | 是否必须 |                             含义                             |
| :-----------: | :------: | :----------------------------------------------------------: |
| appid |   必须   |                 应用的appid                 |
|   appkey   |   必须   |            应用密钥             |
| code  |   必须   | code作为换取用户信息的票据，每次用户授权带上的code将不一样，code只能使用一次，10分钟未被使用自动过期。 |

### 2.1返回参数说明

| 参数说明 |       描述        |
| :------: | :---------------: |
|   code   | 返回码;0:返回成功 |
|   msg    |     返回信息      |
|   data   |  返回结果(数据)   |

#### 2.1.1data结果说明

| 参数说明  | 类型   | 描述                         |
| --------- | ------ | ---------------------------- |
| typeId    | int    | 互联登录方式                 |
| loginType | String | 互联登录方式中文             |
| appid     | String | 应用appid                    |
| openId    | String | 飛宇互联用户唯一id           |
| name      | String | 第三方互联用户昵称           |
| avatar    | String | 用户头像                     |
| gender    | int    | 用户性别(1:男,0:女)          |
| genderStr | String | 用户性别                     |
| province  | String | 城市(百度登录为用户登录城市) |







**注:暂时申请平台还未开发，功能模块已实现**

需要的请发送邮箱fy@0fy0.com