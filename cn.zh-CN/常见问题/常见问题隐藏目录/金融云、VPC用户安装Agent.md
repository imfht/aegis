# 金融云、VPC用户安装Agent {#concept_40471_zh .concept}

针对无法直接连通公网的云服务器（如阿里金融云上的服务器、或使用专有网络VPC的云服务器） ，您可通过以下步骤安装安骑士Agent。

## 安装步骤 {#section_fsr_1kb_3gb .section}

**说明：** 如果您已在服务器上安装了安全软件（如安全狗、云锁等），可能会导致安骑士Agent插件无法正常安装。建议您在安装安骑士Agent插件前确认您的服务器上是否存在这类安全软件，如果存在建议您先关闭、或卸载该安全软件之后，再安装安骑士Agent插件。

1.  登录[云盾服务器安全（安骑士）管理控制台](https://yundun.console.aliyun.com/?p=aqs#/)，单击**设置**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82028/154874102035654_zh-CN.png)

2.  单击**安装/卸载**进入安装安骑士Agent页面。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82028/154874102035655_zh-CN.png)

3.  根据您的服务器操作系统选择安装步骤，安装最新版本的安骑士Agent插件。
    -   **Windows系统** 
        1.  在安装安骑士Agent页面，单击**点击下载**下载最新版本安骑士Agent插件安装文件到本地计算机。
        2.  将安装文件上传至您的Windows服务器，例如通过FTP工具将安装文件上传到服务器。
        3.  在您的Windows服务器上以管理员权限运行安骑士Agent插件安装程序。
        4.  非阿里云服务器输入安装验证Key。

            您可在云盾安装安骑士页面找到您的安装验证Key。

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82028/154874102035656_zh-CN.png)

            **说明：** 

            -   安装验证Key将用于关联您的阿里云账号，在云盾安骑士管理控制台登录您的阿里云账号即可保护您的服务器安全。
            -   每个安装验证Key有效期为1小时，超过该时间将无法正确安装安骑士Agent插件。安装插件前请及时刷新安装验证Key。
        5.  完成安装。
        6.  单击**立即查看**打开资产列表，查看资产在线状态。

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82028/154874102035658_zh-CN.png)

    -   **Linux系统** 

        1.  根据您服务器的Linux系统版本，单击以下链接将安骑士Agent安装程序下载至本地计算机。
            -   **Linux 32位系统**： [安骑士Agent安装程序](https://aegis.alicdn.com/download/AliAqsInstall_32.sh) 
            -   **Linux 64位系统**： [安骑士Agent安装程序](https://aegis.alicdn.com/download/AliAqsInstall_64.sh) 
        2.  将安骑士Agent安装程序上传至您的Linux服务器，例如通过FTP工具将安装文件上传到服务器。
        3.  以管理员身份登录您的Linux服务器。
        4.  定位到您已上传的安骑士Agent安装程序所在目录，根据您的服务器的Linux系统版本，执行以下命令安装安骑士Agent。
            -   **Linux 32 位系统**：`chmod +x AliAqsInstall_32.sh && ./AliAqsInstall_32.sh xxxxxx` 
            -   **Linux 64 位系统**：`chmod +x AliAqsInstall_64.sh && ./AliAqsInstall_64.sh xxxxxx` 
        **说明：** 此安装命令末尾处的`xxxxxx`为安装验证Key，执行安装命令时请用您云盾安装安骑士页面中显示的六位安装验证Key替换`xxxxxx`部分。此安装验证Key与Windows系统安装步骤中的安装验证Key一致。该安装验证Key将用于关联您的阿里云账号，在云盾安骑士管理控制台登录您的阿里云账号即可保护您的服务器安全。

4.  安骑士Agent插件安装完成约五分钟后，您即可在云盾安骑士管理控制台中查看您服务器的在线情况，您的服务器状态将会从离线变成在线。

## 验证Agent安装 { .section}

在您成功安装安骑士Agent后，建议您参考以下步骤进行验证：

1.  检查您的服务器上安骑士Agent的AliYunDun和AliYunDunUpdate这两个进程是否正常运行。关于安骑士Agent进程说明，请参考[Agent说明](../../../../../cn.zh-CN/用户指南/Agent 插件/什么是安骑士Agent插件.md#)。
2.  在您的服务器上，执行以下telnet命令检查您的服务器是否能正常连通安骑士服务器。

    **说明：** 确保以下两个服务器都能连通。

    -   `telnet jsrv3.aegis.aliyun.com 80` 
    -   `telnet update3.aegis.aliyun.com 80` 

如果安骑士Agent安装验证失败，请参考[Agent离线排查](../../../../../cn.zh-CN/用户指南/Agent 插件/Agent 离线排查.md#)。

