---
title: "YC报表中如何实现同比/环比增长"
nodeId: a9E05BDRVQ6L3R7yHmEBBvvDJ63zgkYA
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/a9E05BDRVQ6L3R7yHmEBBvvDJ63zgkYA?utm_scene=team_space"
updateTime: 1778555626000
exportedAt: 2026-05-14T11:46:58.020Z
source: dingtalk-document-mcp
---
## 1、展示同比

以月度同比为例，举例：



![Picture 1](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbYaG8NJOm9/img/bc7b7ec3-7302-4816-80bc-c1de061ba17c.png?Expires=1778766418&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=QC6VN4McDPBqoNUiVb1XInp4wTs%3D "")

数据整理后得

| **月份** | **25年回款（业务日期为25年）** | **同比24年回款（业务日期为24年）** |
|----------|-----------------------------------------|-----------------------------------------------|
| 3月 | 100 | 100 |
| 4月 | 400 | 300 |
| 5月 | 500 | 400 |

要将25年的数据和24年的数据，按照月份做对比，可以借助YC报表的分析维度‘聚合日期-月’，但是需要将业务日期往后\+1年，故



![Picture 2](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbYaG8NJOm9/img/63d74c2e-2903-49f5-ab5a-e199db327e50.png?Expires=1778766418&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=UETVyBN3DctcwIOH8wpBx6798r4%3D "")



![Picture 3](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbYaG8NJOm9/img/8aae4e7d-f372-4c5c-ae1f-6f360d914496.png?Expires=1778766418&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=%2FdhpQujxAudEukpGfmBgbJHx8RE%3D "")



![Picture 4](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbYaG8NJOm9/img/36bb8b9d-1459-400c-b690-3e0c767af9d6.png?Expires=1778766418&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=g%2B2hNoH%2F1suOSKctQPF7m%2F%2FT4lg%3D "")



![Picture 5](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbYaG8NJOm9/img/e9009055-2e1a-4669-8aee-e18d5ff70c9a.png?Expires=1778766418&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=TTZqUFHzQOyVk%2BgO8f2Tjhg5HxU%3D "")



![Picture 6](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbYaG8NJOm9/img/89356141-6e52-4d15-944d-5cfc43df1749.png?Expires=1778766418&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=5SgCUkd4dcNQMEamEilt%2BNkAOF8%3D "")

YC报表中配置如下：



![Picture 7](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbYaG8NJOm9/img/79425b42-4bef-401b-89a3-2c339ab6d065.png?Expires=1778766418&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=obto1ea8HrjGR9bRHndygTmmLUs%3D "")



![Picture 8](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbYaG8NJOm9/img/fac529ae-e358-44c3-a830-079fee774685.png?Expires=1778766418&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=xRX0S%2Bff5cme9L%2FITBFIXsmV614%3D "")



![Picture 9](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbYaG8NJOm9/img/97eacbdd-b8c2-41ed-9c5e-ad81f0090d24.png?Expires=1778766418&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=CwQn1duZ%2BztpwhCkq0iiIJw%2BNlk%3D "")

**若要分析年度同比，同理，只需要在YC中，将分析维度改为‘聚合日期-年’**



![Picture 10](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbYaG8NJOm9/img/fdcf936a-4d3f-4bfa-bfc2-5581c665fb03.png?Expires=1778766418&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=7WLKcHss5H03jrpEl%2FeZHW37vEs%3D "")

## 2、展示环比

还是以月度环比为例：



![Picture 11](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbYaG8NJOm9/img/e46983a2-c220-4bfa-a827-fc6780149469.png?Expires=1778766418&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=Jx7jmKZHrfll9%2FjA5sDxqCo%2Fy9o%3D "")

数据整理后得

| **月份** | **本月** | **上月** |
|----------|----------|----------|
| 3月 | 100 | - |
| 4月 | 400 | 100 |
| 5月 | 500 | 400 |

要将本月的数据和上月的数据，按照月份做对比，可以借助YC报表的分析维度‘聚合日期-月’，但是需要将业务日期往后\+1月，故



![Picture 12](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbYaG8NJOm9/img/820f4345-e19d-4ab0-a28e-d525070467f6.png?Expires=1778766418&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=eSqCG8xu6d2rTutH5PnBNyeLShU%3D "")



![Picture 13](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbYaG8NJOm9/img/767fc5e2-bb59-4adb-aa73-28e982736937.png?Expires=1778766418&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=cu762hYNqEuchhiExRryyCy1dc0%3D "")



![Picture 14](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbYaG8NJOm9/img/474ed90e-42e7-4428-9e5f-d43896ae32f3.png?Expires=1778766418&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=yH6QEjzkgOiJhHPDrYjAtAsF%2Brs%3D "")



![Picture 15](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbYaG8NJOm9/img/c8a885bf-5505-42f5-bd40-4ff6a6cf2694.png?Expires=1778766418&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=0%2FvhxiUIqzSeNyGOVHnNw5y01Ao%3D "")



![Picture 16](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbYaG8NJOm9/img/cda529d6-1e9f-4dba-9057-85c61974bacb.png?Expires=1778766418&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=8CyT4fmJ%2F93nCUGoojbptt6nCqQ%3D "")

YC报表中配置如下：



![Picture 17](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbYaG8NJOm9/img/79425b42-4bef-401b-89a3-2c339ab6d065.png?Expires=1778766418&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=obto1ea8HrjGR9bRHndygTmmLUs%3D "")



![Picture 18](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbYaG8NJOm9/img/dbee058b-0bfe-439d-96a8-682c21f50e08.png?Expires=1778766418&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=D5xjSkwBKgkNMoZyz%2FeE264kZz8%3D "")



![Picture 19](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/Lk3lbmbYaG8NJOm9/img/0e806c4e-0ad1-4d2a-b784-b48812cf83d1.png?Expires=1778766418&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=EdZa0HIEYFXoorqZZBMkELeB34U%3D "")
