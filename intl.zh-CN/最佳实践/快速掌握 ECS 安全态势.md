# 快速掌握 ECS 安全态势 {#concept_94347_zh .concept}

安骑士是一款经受200万+主机稳定性考验的主机安全加固产品，拥有自动化实时入侵威胁检测、病毒查杀、漏洞智能修复、基线一键核查等功能，是构建主机安全防线的统一管理平台。

安骑士基础版功能详情参见[功能特性](../../../../../intl.zh-CN/产品简介/功能列表.md#)。

安骑士功能优势参见[产品优势](../../../../../intl.zh-CN/产品简介/产品优势.md#)。

您可以打开ECS控制台概览页面，单击**安全概览**模块下面的阿里云云盾图标![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82026/155531185335756_zh-CN.png)跳转到安骑士总览页面，查看ECS的安全详情。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82026/155531185335757_zh-CN.png)

跳转到安骑士控制台总览页后，您可在总览页面查看待处理的告警事件数量及其紧急程度、检测到的告警事件总数、已处理事件的数量等信息。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82026/155531185335758_zh-CN.png)

单击待处理告警事件可进入对应的功能进行快速处理：

-   异常登录
-   网站后门

## 查看ECS实例安全详情 { .section}

您可以打开ECS控制台实例页面，单击**实例列表**中的阿里云云盾图标![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82026/155531185335759_zh-CN.png)跳转到安骑士控制台资产列表页面，查看单个ECS实例的安全详情。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82026/155531185435760_zh-CN.png)

跳转到安骑士控制台后，在资产列表页面查看单个ECS实例的安全详情。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82026/155531185435761_zh-CN.png)

ECS实例的安全详情包含：

-   基本信息：

    包括ECS实例名称、ID、所在地区、公网/内网IP地址、主机操作系统、安骑士保护在线状态和分组信息等。

-   漏洞信息：

    检测ECS实例的系统漏洞和Web-CMS漏洞。

-   基线检查：

    检测ECS的系统、数据库、账号配置存在的风险点。

-   异常登录：

    检测ECS上的登录行为，对于在非常用登录地的登录行为提供告警。

-   网站后门：

    检测ECS上是否存在Webshell后门文件。

-   主机异常：

    检测ECS上是否存在异常事件并对异常事件进行处理。

-   主机指纹：

    检测ECS上包含监听端口号、网络协议、对应进程和绑定监听IP等信息。

-   安全配置：

    对漏洞管理、基线检查和登录安全设置进行配置。


