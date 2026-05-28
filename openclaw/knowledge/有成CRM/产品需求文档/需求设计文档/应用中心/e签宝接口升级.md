---
title: "e签宝接口升级"
nodeId: oP0MALyR8k79kzMNhQm5Md7p83bzYmDO
workspaceId: R2PmK2Q8rxRbeXvp
docUrl: "https://alidocs.dingtalk.com/i/nodes/oP0MALyR8k79kzMNhQm5Md7p83bzYmDO?utm_scene=team_space"
updateTime: 1776910737000
exportedAt: 2026-05-14T11:48:41.373Z
source: dingtalk-document-mcp
---
### **需求背景**

1、企业需要实现签署自动落章--本期暂不实现

[https://open.esign.cn/doc/opendoc/file-and-template3/megwsgkmpbg1tec](https://open.esign.cn/doc/opendoc/file-and-template3/megwsgkmpbg1tec1)

2、其他类型文件也需要能够发起签署

3、其他平台也想使用e签宝

### **需求详情**

原先使用的接口：[https://www.yuque.com/esign/potnnf/ggggqh?#xr20G](https://www.yuque.com/esign/potnnf/ggggqh?#xr20G)

新接口：[https://open.esign.cn/doc/opendoc/auth3/ytn2tt](https://open.esign.cn/doc/opendoc/auth3/ytn2tt)

原始需求文档：

[http://smbding.superboss.cc/w%E6%9C%89%E6%88%90CRM2020%E5%85%AD%E6%9C%88%E8%BF%AD%E4%BB%A3%EF%BC%88%E7%80%9A%E6%B5%B7%EF%BC%89/%E5%AF%B9%E6%8E%A5E%E7%AD%BE%E5%AE%9D20201203/#g=1&p=%E9%9C%80%E6%B1%82%E6%A6%82%E8%BF%B0](http://smbding.superboss.cc/%E6%9C%89%E6%88%90CRM2020%E5%85%AD%E6%9C%88%E8%BF%AD%E4%BB%A3%EF%BC%88%E7%80%9A%E6%B5%B7%EF%BC%89/%E5%AF%B9%E6%8E%A5E%E7%AD%BE%E5%AE%9D20201203/#g=1&p=%E9%9C%80%E6%B1%82%E6%A6%82%E8%BF%B0)

### **已明确事项**

1、判断企业是否开通e签宝微应用的接口

答：对接V3时，不需要此判断

2、V3接口如何处理下单、查询套餐余量

答：无法通过接口下单，需要小雾找他们商务下单；没有套餐余量查询接口，应用中无法显示剩余份数

3、获取应用授权页面地址接口有什么变化

答：需要传入orgId/orgName，redirectConfig不传此参数默认页面仅实名认证，不需要授权；

老版切换新版本企业需要重新授权（有新增授权）

4、机构认证信息查询接口有什么变化

答：orgId/orgName/orgIDCardNum\+orgIDCardType(三选一)

5、个人认证信息查询接口有什么变化

答：psnId/psnAccount（手机号/邮箱）/psnIDCardNum\+psnIDCardType(三选一)

6、个人认证/授权接口有什么变化

答：psnId/psnAccount（手机号/邮箱），redirectConfig不传此参数默认页面仅实名认证，不需要用户授权

不需要个人新增授权

#### **1、钉钉已开通e签宝企业可切换至新版e签宝**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/jP2lRYj21r6BBO8g/img/b1e6a8c3-744e-494e-a09b-c5c2dcfc29ca.png?Expires=1778766521&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=sYtCsBYRF26JNxFStG%2Fm5T2Xe3E%3D "")

#### **2、功能上线后，企微/飞书平台\+钉钉后续要开通e签宝企业**

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/jP2lRYj21r6BBO8g/img/c21a2395-f2be-4c80-9081-292dc9383264.png?Expires=1778766521&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=ounTGXUyvUkCnPGdRpy53HjeCo4%3D "")

#### **3、crm内支持选择更多类型文件发起签署---仅新版**

优化前：支持选择pdf、doc、docx格式文件

优化后：增加支持选择png、jpg、jpeg、jfif、xlsx、xls格式文件（这类文件都需要转化为pdf，即上传文件接口传"convert2Pdf":true）

**4、发起签署，人员认证查询异常提示**

1、员工中字段被选择作为人员认证状态查询入参，则字段不允许删除，删除时提示‘该字段被选择作为e签宝个人认证查询传参，不允许删除（可前往应用中心-电子签章-签署配置中更改配置后删除）’

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/jP2lRYj21r6BBO8g/img/8c1b9aad-4ebe-491c-9305-0ba660d33598.png?Expires=1778766521&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=u5jBWOULgfFi%2BfwEcytpLQc4JZA%3D "")

2、电话号码为空、格式不对等导致个人认证查询失败，提示如下

![image.png](https://alidocs2.oss-cn-zhangjiakou.aliyuncs.com/res/jP2lRYj21r6BBO8g/img/dc6b5d7a-67ed-4efa-9c31-9214b088f1e4.png?Expires=1778766521&OSSAccessKeyId=LTAI5tKTjg4Kq1HCdBJ8qpSp&Signature=UNxDkJyFeF%2FjpMBWwl1avYvEfNs%3D "")

#### **附：新旧接口映射**

[接口对比表](https://alidocs.dingtalk.com/i/nodes/dQPGYqjpJYg0lZOdIoZ7rKzeWakx1Z5N?utm_scene=team_space&iframeQuery=sheet_range%3Dkgqie6hm_0_0_1_1)





下面这个文件残缺，不需要：

| **接口类型** | **功能模块** | **旧接口名称** | **旧接口地址** | **旧接口入参(必传)** | **旧接口出参** | **新接口名称** | **新接口地址** | **新接口入参(必传)** | **新接口出参** | **新接口链接** | **差异分析** |
|---------------------------------------------------------------------------|---------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------|
| **鉴权认证类** | 企业授权 | 获取授权的页面地址 | POST /v1/ding/auth/url | <ul><li>corpId(是)</li><br><li>redirectUrl(是)</li></ul> | <ul><li>taskId</li><br><li>pcUrl</li><br><li>mobileUrl</li></ul> | 获取机构认证&授权页面链接 | POST /v3/org-auth-url | <ul><li>orgName/orgId(二选一)</li><br><li>redirectConfig(可选)</li></ul> | <ul><li>authUrl</li><br><li>authShortUrl</li><br><li>auth  FlowId</li></ul> | [获取机构认证&授权页面链接](https://open.esign.cn/doc/opendoc/auth3/kcbdu7) | **重大变化**<br>1\. 参数结构完全重构,增加了授权范围配置<br>2\. 支持多种认证方式和授权权限配置<br>3\. 返回长短链接,有效期30天 |
| **鉴权认证类** | 企业状态 | 获取企业e签宝微应用状态 | GET /v1/ding/isv/corp/status | <ul><li>corpId(是)</li></ul> | <ul><li>installStatus</li><br><li>authStatus</li></ul> | 无直接对应接口 | - | - | - | - | **功能移除**<br>不需要开通微应用，是云服务 |
| **套餐管理类** | 套餐转售 | 套餐转售1(分润模式) | POST v1/ding/channel/order | <ul><li>corpId(是)</li><br><li>orderId(是)</li><br><li>itemCode(是)</li><br><li>itemName(是)</li><br><li>quantity(是)</li><br><li>orderCreateTime(是)</li></ul> | <ul><li>esignOrderId</li></ul> | 无直接对应接口 | - | - | - | - | **功能重构**<br>V3套餐管理方式发生重大变化,需要使用新的订单管理接口 |
| **套餐管理类** | 套餐查询 | 查询套餐余量 | GET v1/ding/contract/margin | <ul><li>corpId(是)</li></ul> | <ul><li>margin(number)</li></ul> | 无直接对应接口 | - | - | - | - | **功能重构**<br>V3套餐查询方式变化,需要联系e签宝获取新的查询接口 |
| **用户信息查询类** | 企业信息 | 查询企业信息 | GET /v1/ding/corp/info | <ul><li>corpId(是)</li></ul> | <ul><li>isRealName</li><br><li>orgName</li></ul> | 查询机构认证信息 | GET /v3/organizations/identity-info | <ul><li>orgId/orgName/orgIDCardNum\+orgIDCardType(三选一)</li></ul> | <ul><li>realnameStatus</li><br><li>orgId</li><br><li>orgInfo</li><br><li>authorizeUserInfo</li></ul> | [查询机构认证信息](https://open.esign.cn/doc/opendoc/auth3/xxz4tc) | **功能增强**<br>V3返回更详细的企业信息和授权状态 |
| **用户信息查询类** | 个人信息 | 查询个人信息 | GET /v1/ding/user/info | <ul><li>corpId(是)</li><br><li>userId(是)</li></ul> | <ul><li>isRealName</li><br><li>userName</li></ul> | 查询个人认证信息 | GET /v3/persons/identity-info | <ul><li>psnId/psnAccount（手机号/邮箱）/psnIDCardNum\+psnIDCardType(三选一)</li></ul><br>---备注：psnAccount取值，根据e签宝配置中‘人员认证手机号取自’的配置，有多个手机号取第一个 | <ul><li>realnameStatus</li><br><li>psnId</li><br><li>psnInfo</li></ul> | [获取个人认证&授权页面链接](https://open.esign.cn/doc/opendoc/auth3/rx8igf) | **功能增强**<br>V3支持多种查询方式,返回更详细的个人信息 |
| **鉴权认证类** | 个人实名 | 获取跳转到个人实名的地址 | POST /v1/ding/user/realname | <ul><li>corpId(是)</li><br><li>userId(是)</li><br><li>redirectUrl(否)</li></ul> | <ul><li>taskId</li><br><li>pcUr</li><br><li>mobileUrl</li></ul> | 获取个人认证&授权页面链接 | POST /v3/psn-auth-url | <ul><li>psnAccount/psnId(二选一)</li><br><li>psnAuthConfig(可选)</li></ul> | <ul><li>authUrl</li><br><li>authShortUrl</li><br><li>authFlowId</li></ul> | [获取个人认证&授权页面链接](https://open.esign.cn/doc/opendoc/auth3/rx8igf) | **功能增强**<br>V3支持多种认证方式配置和授权范围设置 |
| **鉴权认证类** | 企业实名 | 获取跳转到企业实名的地址 | POST /v1/ding/corp/realname | <ul><li>corpId(是)</li><br><li>userId(是)</li><br><li>redirectUrl(否)</li></ul> | <ul><li>taskId</li><br><li>pcUrl</li><br><li>mobileUrl</li></ul> | 获取机构认证&授权页面链接 | POST /v3/org-auth-url | <ul><li>orgName/orgId(二选一)</li><br><li>orgAuthConfig(可选)</li></ul> | <ul><li>authUrl</li><br><li>authShortUrl</li><br><li>authFlowId</li></ul> | [获取机构认证&授权页面链接](https://open.esign.cn/doc/opendoc/auth3/kcbdu7) | **功能增强**<br>V3支持多种企业认证方式,包括法人认证、对公打款等 |
| **文件管理类** | 文件上传 | 通过上传方式创建文件 | POST /v1/ding/files/getUploadUrl | <ul><li>contentMd5(是)</li><br><li>contentType(是)</li><br><li>convert2Pdf(是)</li><br><li>fileName(是)</li><br><li>fileSize(是)</li></ul> | <ul><li>fileId</li><br><li>uploadUrl</li></ul> | 上传本地文件 | POST /v3/files/file-upload-url | <ul><li>fileName(是)</li><br><li>contentMd5(是)</li><br><li>contentType(是)</li></ul> | <ul><li>fileId</li><br><li>fileUploadUrl</li></ul> | [上传本地文件](https://open.esign.cn/doc/opendoc/pdf-sign3/rlh256) | **参数简化**<br>V3移除了convert2Pdf和fileSize必传参数,流程更简化 |
| **文件管理类** | 文件查询 | 查询文件详情/下载文件 | GET /v1/files/\{fileId\} | <ul><li>fileId(path)</li></ul> | <ul><li>fileId</li><br><li>name</li><br><li>size</li><br><li>status</li><br><li>downloadUrl</li><br><li>pdfTotalPages</li></ul> | 查询文件上传状态 | GET /v3/files/\{fileId\} | <ul><li>fileId(path)</li></ul> | <ul><li>fileId</li><br><li>fileName</li><br><li>fileSize</li><br><li>status</li><br><li>downloadUrl</li></ul> | [文件和模板服务API V3](https://open.esign.cn/doc/opendoc/codemsg-v3/px5yvgqf9glbs7o6) | **功能保持**<br>V3基本保持了V1的查询功能,参数结构略有调整 |
| **签署流程类** | 获取发起签署任务地址 | 获取发起签署任务地址 | POST /v1/ding/process/start | <ul><li>**files**</li><br><li style="margin-left:1em">fileId</li><br><li style="margin-left:1em">fileName</li></ul> | <ul><li>taskId</li><br><li>pcUrl</li><br><li>mobileUrl</li></ul> | 基于文件发起签署 | POST /v3/sign-flow/create-by-file | <ul><li>**docs**</li><br><li style="margin-left:1em">fileId</li><br><li style="margin-left:1em">fileName</li><br><li>signFlowConfig</li><br><li style="margin-left:1em">signFlowTitle</li></ul> | <ul><li>code</li></ul> | [基于文件发起签署](https://open.esign.cn/doc/opendoc/pdf-sign3/nxhgcl3bfgqz8qlz) | **重大变化**<br>1\. V3采用统一的签署流程管理<br>2\. 新增签署方配置signers参数<br>3\. 支持更多签署方式和参数配置 |
| **签署流程类** | 获取签署人签署地址 | 获取签署人签署地址 | POST /v1/ding/process/start | <ul><li>corpId(是)</li><br><li>taskId(是)</li></ul> | <ul><li>pcUrl</li><br><li>mobileUrl</li></ul> | 获取签署人签署地址 | POST /v3/sign-url | <ul><li>signFlowId(是)</li><br><li>accountId(是)</li></ul> | <ul><li>signUrl</li></ul> | [V3文档](https://open.esign.cn/doc/opendoc/sign-flow3/xp856s) | **参数简化**<br>V3简化了参数，signFlowId和accountId替代了V1的多个参数 |
| **签署流程类** | 获取对应流程任务详情 | 获取对应流程任务详情 | GET /v1/ding/order/detail | <ul><li>corpId(是)</li><br><li>taskId(是)</li></ul> | <ul><li>flowStatus</li><br><li>**logs**</li><br><li style="margin-left:1em">operatorAccountName</li><br><li style="margin-left:1em">logType</li><br><li style="margin-left:1em">operateDescription</li><br><li style="margin-left:1em">operateTime</li></ul> | 查询签署流程详情 | GET /v3/sign-flow/\{signFlowId\} | <ul><li>signFlowId(path)</li></ul> | <ul><li>signFlowInfo</li><br><li>signTaskInfos</li><br><li>fileInfos</li></ul> | [V3文档](https://open.esign.cn/doc/opendoc/sign-flow3/kn380p) | **信息更丰富**<br>V3返回更详细的流程信息和签署状态 |
| **签署流程类** | 获取流程任务合同列表 | 获取流程任务合同列表 | GET /v1/ding/flow/docs | <ul><li>corpId(是)</li><br><li>taskId(是)</li></ul> | <ul><li>**docs**</li><br><li style="margin-left:1em">fileId</li><br><li style="margin-left:1em">fileName</li><br><li style="margin-left:1em">fileUrl</li></ul> | 查询合同列表 | GET /v3/contracts | <ul><li>contractIds(是)</li></ul> | <ul><li>contracts</li></ul> | [V3文档](https://open.esign.cn/doc/opendoc/contract3/ln452t) | **功能增强**<br>V3支持更多合同查询和管理功能 |






