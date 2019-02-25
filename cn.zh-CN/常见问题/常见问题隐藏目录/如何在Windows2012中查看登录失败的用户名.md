# 如何在Windows2012中查看登录失败的用户名 {#concept_53698_zh .concept}

由于Windows 2012 远程桌面服务开启了SSL安全层，安全日志无法记录登录失败的源IP和用户名。因此，安骑士的暴力破解拦截功能也无法获取对方用户名。但是，您可以手动分析、获取登录失败的用户名。

## 前提条件 {#section_jkv_fnc_3gb .section}

手动分析获取登录失败用户名的前提条件是：Windows 2012已经打开审核登录事件日志。您可以：

-   在**控制面板** \> **系统和安全** \> **管理工具** \> **事件查看器**中，查看日志功能是否启用并记录。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82051/154874116535719_zh-CN.jpg)

-   在**控制面板** \> **系统和安全** \> **管理工具**中，开启审核登录事件，审核账户登录事件。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82051/154874116535720_zh-CN.jpg)


## 操作步骤 { .section}

在安骑士**入侵检测** \> **异常登录**的记录中，**对方用户名**记录为**N/A**。参照以下步骤手动分析，获取登录失败的用户名。

1.  登录[云盾服务器安全（安骑士）管理控制台](https://yundun.console.aliyun.com/?p=aqs#/)，并前往资产列表。
2.  找到目标服务器，单击其**异常登录**菜单下的告警数字，进入异常登录页面。
3.  找到**爆破登录**告警记录，查看其**登录时间**（该记录的**对方用户名**为**N/A**）。
4.  登录Windows 2012服务器，打开**控制面板** \> **系统和安全** \> **管理工具** \> **事件查看器**，并查找**Windows日志** \> **安全**。
5.  查找安骑士提示爆破登录时刻的明细日志。搜索关键字为**审核失败**，任务类别为**登录**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82051/154874116535721_zh-CN.png)

6.  在常规选项中查看失败原因：未知用户名或密码错误。其中，用户名选项为登录失败的用户。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82051/154874116535722_zh-CN.png)


