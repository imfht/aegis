# 什么是安骑士Agent插件？ {#concept_31778_zh .concept}

Agent是安骑士部署到云服务器操作系统中的轻量化进程，主要功能是根据用户配置的安全策略上报服务器存在的安全风险和新增的安全事件数据，同时响应用户和安骑士云端防护中心的指令，实现对云服务器上的安全威胁清除和恶意攻击拦截。

## 工作原理 {#section_zxy_xky_ggb .section}

安骑士 Agent 每隔5小时会主动向安骑士服务器端上报一次在线数据信息。

如果安骑士 Agent 没有按时上报在线信息，安骑士服务器端会及时判定该服务器不在线，且在安骑士管理控制台中该服务器的保护状态会显示为**离线**。

![ECS保护状态离线](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/81986/155385220035502_zh-CN.png)

**说明：** 

-   如果未安装agent，您将无法使用安骑士提供的服务。
-   安骑士Agent与服务端网络连接断开或程序退出都可能导致服务器保护状态**离线**，详情参见Agent离线排查。

## Agent相关进程 { .section}

安骑士 Agent 进程运行账号：

-   **Windows**：Agent进程在Windows 系统的服务器上以**system**账号运行。
-   **Linux**：在Linux系统的服务器上以**root**账号运行。

安骑士 Agent 包含以下两个主要进程：

|Agent进程名称|进程功能|进程所在路径|
|---------|----|------|
|**AliYunDun**|该进程用于与安骑士服务器建立连接。| -   **Windows 32位系统**：

    ```
C:\Program Files\Alibaba\aegis\aegis_client
    ```

-   **Windows 64位系统**：

    ```
C:\Program Files (x86)\Alibaba\aegis\aegis_client
    ```

-   **Linux 系统**：

    ```
/usr/local/aegis/aegis_client
    ```


 |
|**AliYunDunUpdate**|该进程用于定期检测安骑士Agent是否需要升级。| -   **Windows 32位系统**：

    ```
C:\Program Files\Alibaba\aegis\aegis_update
    ```

-   **Windows 64位系统**：

    ```
C:\Program Files (x86)\Alibaba\aegis\aegis_update
    ```

-   **Linux 系统**：

    ```
/usr/local/aegis/aegis_update
    ```


 |
| | | |

## 资源占用 { .section}

安骑士Agent仅占用您服务器少量资源：

-    **业务优先模式**： 安骑士Agent占用不超过1%CPU及50MB内存。
-   **防护优先模式** ： 安骑士Agent占用不超过10%CPU及80MB内存。

您可在安骑士控制台定位到**设置** \> **安全配置** \> **Agent插件**，在**Agent插件**模块可查看Agent不同优先模式运行的服务器数量。

单击**管理**可将您的服务器设置为**业务优先模式**或**防护优先模式**。

![agent插件](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/31778/cn_zh/1540915699303/Agent%E6%8F%92%E4%BB%B6%E6%A8%A1%E5%BC%8F.png)

**说明：** 如果占用资源超过防护优先模式峰值，安骑士Agent将会暂停工作。CPU占用下降到合理范围内后Agent会自动重启。

