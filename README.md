# APISpace 介绍
**本 API 服务由 [APISpace（apispace.com）](https://www.apispace.com/?utm_source=github&utm_term=yunyingshangsanxiangxi) 提供。**

APISpace 是 Eolink 旗下专业的 API 开放与交易平台，为广大企业以及个人开发者提供多维度、全方位的API接口，覆盖短信验证、天气查询、快递物流、OCR文字识别等海量 API 服务，帮助用户快速获取数据，降低获取数据的成本和难度，提升开发效率。

APISpace 提供15种开发语言的代码示例，分别是：
- Java(OK HTTP)
- HTTP
- cURL
- 微信小程序
- PHP(pecl_http)、PHP(cURL)
- Python(http.client)、Python(Requests)
- JavaScript(Jquery AJAX)、JavaScript(XHR)
- NodeJS(Native)、NodeJS(Request)
- Ruby(Net:Http)
- Shell(Httpie)、Shell(cUrl)

# 运营商三要素详细版
输入姓名、身份证号码、手机号码，验证此三种信息是否一致，返回验证结果、手机归属地、运营商名称。

**使用该产品前，您需要通过 [https://www.apispace.com/eolink/api/carriers-pro/introduction](https://www.apispace.com/eolink/api/carriers-pro/introduction?utm_source=github&utm_term=yunyingshangsanxiangxi) 申请API服务**

本文档末尾提供了 Python(Requests) 的调用代码示例，可以前往文档末尾查看。

更多代码示例：[https://www.apispace.com/eolink/api/carriers-pro/guidence/](https://www.apispace.com/eolink/api/carriers-pro/guidence/?utm_source=github&utm_term=yunyingshangsanxiangxi)

相比于运营商三要素 API，运营商三要素详细版API 会返回认证不通过的详细原因。

-   点击查看 [运营商三要素](https://www.apispace.com/eolink/api/carriers/introduction?utm_source=github&utm_term=yunyingshangsanyaosu)


### 返回示例

```
{
    "chargeStatus":" 1",
    "message":"成功",
    "data":{
        "orderNo":"011569554991100011",
        "handleTime":"2018-10-26 10:11:41",
        "type":" 2",
        "result":"02",
        "gender":"1",
        "age":"30",
        "remark":"认证不一致",
        "detail":{
            "code":"02",
            "remark":"手机号已实名，但是身份证和姓名均与实名信息不一致"
        }
    },
    "code":"200000"
}
```

### 应用场景

1.  #### 金融行业

银行、支付机构、P2P网贷等金融机构需要进行用户身份验证，以确保资金的安全。运营商三要素认证是一种较为安全和快速的验证方式，常被应用于网上银行、交易平台、投资理财等业务中。

2.  #### 实名制管理

为了保障公共安全和社会稳定，各级政府部门也开始推行实名制管理。运营商三要素认证可以有效地验证用户的真实身份信息，被广泛应用于政务、社保、医疗、公积金等领域。

3.  #### 网络游戏

为保障游戏的公平性和防止游戏作弊，网络游戏平台需要验证用户的真实身份信息。运营商三要素认证被应用于多款网络游戏中，如《英雄联盟》、《王者荣耀》、《穿越火线》等。

### 服务保障
![image](https://user-images.githubusercontent.com/36323798/223989801-a89aee72-5eba-4b43-9520-7fc10c7f56a5.png)

### Python(Requests) 调用代码示例

```
import requests

url = "https://eolink.o.apispace.com/carriers-pro/carriers-auth-detail"

payload = {"name":"","idNum":"","mobile":""}

headers = {
    "X-APISpace-Token":"",
    "Authorization-Type":"apikey",
    "Content-Type":"application/x-www-form-urlencoded"
}

response=requests.request("POST", url, data=payload, headers=headers)

print(response.text)

```
