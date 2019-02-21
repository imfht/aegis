# Linux软件漏洞修复命令为空 {#concept_59377_zh .concept}

当您在安骑士漏洞管理中，选择某Linux软件漏洞，单击生成修复命令时，生成的漏洞修复命令为空。您可以参照本文介绍的解决方案。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82035/155073922935697_zh-CN.png)

## 解决方案 { .section}

您可以通过以下方案进行排查，解决该问题：

-   检查安骑士 Agent 版本是否过低。

    如果您服务器上的安骑士 Agent 版本过低，可能不支持漏洞扫描功能。如果您的安骑士 Agent 没有正常自动更新，建议您参考[安装Agent](../../../../../cn.zh-CN/.md#) 手动安装最新版安骑士 Agent。

-   检查安骑士 Agent 是否离线。

    如果您服务器上的安骑士 Agent 显示为离线，您将无法通过漏洞管理功能生成修复命令。建议您参考[Agent 离线排查](../../../../../cn.zh-CN/用户指南/Agent 插件/Agent 离线排查.md#)进行排查，确保您服务器上的安骑士 Agent 在线。


