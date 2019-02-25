# Agent 离线排查 {#concept_31776_zh .concept}

本文档介绍了安骑士 Agent 处于离线状态时如何进行问题排查和处理。

## 问题描述 {#section_rht_4qz_ggb .section}

安骑士控制台**资产列表**页面中Agent处于**离线**状态。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/81988/155106464435753_zh-CN.png)

## 问题排查 {#section_pc1_pqz_ggb .section}

建议按照以下步骤对Agent离线的问题进行排查：

1.  登录您的服务器查看安骑士 Agent 相关进程是否正常运行。如果Agent 相关进程没有正常运行，建议重启您的服务器，或者[重新安装安骑士Agent](cn.zh-CN/用户指南/Agent 插件/安装Agent.md#)。
    -   **Windows系统**：在任务管理器中查看进程**AliYunDun**和**AliYunDunUpdate**是否正常运行。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/81988/155106464435704_zh-CN.png)

    -   **Linux系统**：执行命令`ps aux | grep AliYunDun`命令查看进程**AliYunDun**和**AliYunDunUpdate**是否正常运行。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/81988/155106464435736_zh-CN.png)

2.  如果首次安装安骑士 Agent 后显示安骑士状态不在线，可参考以下方式重新启动安骑士 Agent：

    -   **Windows系统**：在服务项中定位到以下两个进程服务项并右键单击**重新启动**即可。

        ![aa](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/31776/cn_zh/1505713814118/image.png)

    -   **Linux系统**：执行命令`killall AliYunDun && killall AliYunDunUpdate && /usr/local/aegis/aegis_client/aegis_10_xx/AliYunDun`重启。

        **说明：** 将命令中的`xx`替换为该目录下的最大数字。

    **说明：** 购买ECS实例时勾选**安全加固**选项即可自动安装安骑士Agent。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/81988/155106464435748_zh-CN.png)

3.  检查您的服务器网络连接是否正常。

    -   服务器有公网 IP （如经典网络、EIP、非阿里云主机）
        -   **Windows 系统** ： 在命令行中执行`ping jsrv.aegis.aliyun.com -l 1000`。
        -   **Linux 系统** ： 执行命令`ping jsrv.aegis.aliyun.com -s 1000`。
    -   服务器无公网 IP （只覆盖阿里云ECS，如金融云、VPC 专有网络）
        -    **Windows 系统**： 在命令行中执行`ping jsrv3.aegis.aliyun.com -l 1000`。
        -    **Linux 系统**：
            -   VPC专有网络：在命令行中执行`ping jsrv2.aegis.aliyun.com -s 1000`命令。
            -   国内经典网络：在命令行中执行`ping jsrv4.aegis.aliyun.com -s 1000`命令。
            -   国外经典网络：在命令行中执行`ping jsrv5.aegis.aliyun.com -s 1000`命令。
    **说明：** 连通以上任意一个网络即视为服务器网络连接正常。

4.  如果连接不通，请根据以下方法检查您的服务器网络连接状况：
    -   确认您的服务器的 DNS 服务正常运行。如果 DNS 服务无法运行，请您重启您的服务器或检查服务器 DNS 服务是否有问题。
    -   检查服务器是否设置了防火墙 ACL 规则、或阿里云安全组规则。如果有，请确认已将服务器安全（安骑士）的服务端 IP 加入防火墙白名单（出、入方向均需添加）以允许网络访问。

        将下列 IP 段的 80 端口添加至白名单，最后一个 IP 段需要同时添加 80 和 443 端口至白名单：

        -   10.84.135.0/24 Port: 80 443
        -   106.11.248.0/24 Port: 80 443
        -   106.11.250.0/24 Port: 80 443
        -   100.100.0.0/16 Port: 80 443
    -   检查您的服务器公网带宽是否为零。

        如果您的服务器公网带宽为零，请参考以下步骤进行解决：

        1.  在您服务器的 hosts 文件添加以下域名解析记录：
            -   国内经典网络： `100.100.110.61 jsrv.aegis.aliyun.com`、`100.100.45.131 jsrv.aegis.aliyun.com``100.100.110.62 update.aegis.aliyun.com`和 `100.100.45.29 update.aegis.aliyun.com`
            -   国外经典网络： `100.100.103.52 jsrv.aegis.aliyun.com`、`100.100.30.54 jsrv.aegis.aliyun.com` 、`100.100.30.55 update.aegis.aliyun.com`和`100.100.103.54 update.aegis.aliyun.com`
        2.  修改 hosts 文件后，执行`ping jsrv.aegis.aliyun.com`命令。

            如果返回的结果不是`100.100.25.3`，请重启服务器或检查服务器 DNS 服务是否有问题。

        3.  如果仍然无法解析到正确的 IP，您可以尝试修改安骑士安装目录下 **conf**目录中的 **network\_config** 配置文件，将**t\_srv\_domain**对应值修改为`100.100.30.25`、将**h\_srv\_domain**对应值修改为`100.100.167.125`。修改完成后，重启安骑士 Agent 进程。

            **说明：** 修改前请务必备份**network\_config**配置文件。

            **说明：** 此方法只适用于公网带宽为0且安骑士 Agent 离线的服务器。

        4.  如果 Ping 命令执行解析成功，再次执行 Telnet 命令`telnet 140.205.140.205 80`查看是否能连通解析出的域名 IP 的 80 端口。如果无法连通，请确认防火墙是否存在相关限制。
5.  检查您的服务器 CPU、内存是否长期维持较高占用率（如 95%、100%），此情况可能导致安骑士 Agent 进程无法正常工作。
6.  检查服务器是否已安装第三方的防病毒产品（如安全狗、云锁等）。部分第三方防病毒软件可能会禁止安骑士Agent 插件访问网络。如果有，请暂时关闭该产品并重新安装安骑士 Agent。

