# 登录IP拦截加白 {#concept_93646_zh .concept}

## 设置登录IP拦截加入白名单 { .section}

为避免安骑士对您的正常登录行为进行拦截（例如，多次输入密码错误；或办公网采用统一 IP 作为出口的环境中，多次输入密码错误触发的误拦截等），您可将此类 IP 添加至登录IP拦截白名单中。加入白名单后，安骑士暴力破解拦截功能将不会对来自登录 IP 白名单中的 IP 登录行为进行拦截。

**操作步骤**

1.  登录[云盾服务器安全（安骑士）管理控制台](https://yundun.console.aliyun.com/?p=aqs#/)。
2.  定位到**设置** \> **安全配置**，在安全配置页面单击**登录IP拦截加白**选项右侧的**点此设置**，打开访问白名单页面。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82021/154838196635884_zh-CN.png)

3.  在访问白名单页面单击白名单列表右上角的**添加**，打开添加对话框。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82021/154838196635885_zh-CN.png)

4.  在**源IP**输入框中输入访问来源IP地址。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82021/154838196735886_zh-CN.png)

    **说明：** 设置某源IP加入访问白名单后，该IP对您加入白名单的主机访问将不受任何限制，请谨慎操作。

5.  选中需要添加到登录IP拦截白名单中的主机IP地址，单击**移动**按钮将该主机添加到**已选**区域。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82021/154838196735887_zh-CN.png)

    **说明：** 如果您希望新购的资产自动添加到登录IP拦截白名单中，可勾选**当有新主机购入时，自动共享当前设置**选项。该设置将于一天后生效。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82021/154838196735888_zh-CN.png)

6.  单击**确认**，安骑士暴力破解功能将不再对您选定的IP地址登录行为进行拦截。

## 取消登录IP拦截白名单设置 { .section}

如果您需要对主机解除登录IP拦截白名单设置，可单击访问白名单页面操作栏的**失效**按钮，对目标IP取消登录IP拦截加白的设置。

失效操作支持批量处理。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82021/154838196735889_zh-CN.png)

