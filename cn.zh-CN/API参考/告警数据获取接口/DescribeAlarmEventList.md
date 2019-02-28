# DescribeAlarmEventList {#doc_api_1030334 .reference}

获取态势感知安全告警模块的安全事件的列表。

告警事件分为告警与异常两个维度，一个告警事件包含多个异常事件。此API可以获取告警事件的列表。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=aegis&api=DescribeAlarmEventList)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeAlarmEventList|系统规定参数。取值：DescribeAlarmEventList。

 |
|CurrentPage|Integer|是|1|告警事件列表的页码。起始值：1 默认值：1

 |
|From|String|是|aqs|请求来源标识，固定为aqs。

 |
|PageSize|String|是|20|分页查询时设置的每页行数。默认值: 20。

 |
|AlarmEventName|String|否|DDOS木马|告警事件名称。

 |
|AlarmEventType|String|否|恶意进程（云查杀）|告警事件类型。

 |
|Dealed|String|否|Y|告警事件状态。

 -   N：待处理告警
-   Y：已处理告警

 |
|Lang|String|否|zh|语言参数。

 -   zh：中文
-   cn：英文

 |
|Levels|String|否|serious|告警事件的危险等级，多个严重等级用逗号分隔（严重等级递减）。

 -   serious：紧急
-   suspicious：可疑
-   remind：提醒

 |
|Remark|String|否|database\_server|告警名称/资产。

 |
|SourceIp|String|否|1.1.1.1|请求源IP。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageInfo| | |分页信息。

 |
|└Count|Integer|1|告警事件条数。

 |
|└CurrentPage|Integer|1|告警事件列表的页码。

 |
|└PageSize|Integer|20|分页大小。

 |
|└TotalCount|Integer|1|总条数。

 |
|RequestId|String|28267723-D857-4DD8-B295-0131905BA725|请求ID。

 |
|SuspEvents| | |告警事件的列表。

 |
|└AlarmEventName|String|Linux计划任务执行异常指令|告警事件名称。

 |
|└AlarmEventType|String|进程异常行为|告警事件类型。

 |
|└AlarmUniqueInfo|String|8df914418f4211fbf756efe7a6f40cbc|告警事件的唯一标识。

 |
|└CanBeDealOnLine|Boolean|true|是否能在线处理（隔离）。

 |
|└CanCancelFault|Boolean|false|能否取消标记为误报。

 |
|└DataSource|String|aegis\_suspicious\_event|数据来源。

 |
|└Dealed|Boolean|true|告警事件是否已处理。

 -   true：已处理
-   false：未处理

 |
|└Description|String|黑客入侵服务器后，为了让恶意后门程序能持久化运行，黑客常常将恶意SHELL脚本写入crontab、systemd等计划任务。|告警事件的描述。

 |
|└EndTime|Long|1543740301000|告警事件结束时间。

 |
|└GmtModified|Long|1543740301000|告警事件修改时间，表示同一告警事件再次上报的时间。

 |
|└InstanceName|String|测试服务器|关联实例的名称。

 |
|└InternetIp|String|142.1.1.1|关联实例的公网IP。

 |
|└IntranetIp|String|192.168.1.1|关联实例的私网IP。

 |
|└Level|String|serious|告警事件的危险等级。

 -   serious：紧急
-   suspicious：可疑
-   remind：提醒

 |
|└SaleVersion|String|4|需要的售卖版本。

 -   0：基础版本
-   1：企业版本

 |
|└Solution|String|请及时排查告警中提示的恶意URL，以及所下载的目录下的恶意文件。并及时清理已运行的恶意进程。如果该指令是您自己主动执行，您可以在控制台点击标记为误报，并通过工单方式反馈给我们的安全工程师。|告警事件的处理方法。

 |
|└StartTime|Long|1543740301000|告警事件的开始时间。

 |
|└SuspiciousEventCount|Integer|1|关联的异常事件的条数。

 |
|└Uuid|String|47900178-885d-4fa4-9d77-dba97dba2926|关联实例的唯一标识。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?CurrentPage=1
&From=aqs
&PageSize=20
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeAlarmEventListResponse>
  <RequestId>B5446AFA-58B6-41DC-80E6-E0382AC5A1F4</RequestId>
  <PageInfo>
    <Count>1</Count>
    <TotalCount>1</TotalCount>
    <PageSize>10</PageSize>
    <CurrentPage>1</CurrentPage>
  </PageInfo>
  <SuspEvents>
    <Uuid>47900178-885d-4fa4-9d77-XXXXXXXXXXXX</Uuid>
    <Description>黑客入侵服务器后，为了让恶意后门程序能持久化运行，黑客常常将恶意SHELL脚本写入crontab、systemd等计划任务。</Description>
    <CanCancelFault>false</CanCancelFault>
    <InternetIp>10.0.0.0</InternetIp>
    <SuspiciousEventCount>1</SuspiciousEventCount>
    <AlarmUniqueInfo>8df914418f4211fbf756efe7a6f40cbc</AlarmUniqueInfo>
    <AlarmEventName>Linux计划任务执行异常指令</AlarmEventName>
    <AlarmEventType>进程异常行为</AlarmEventType>
    <IntranetIp>10.0.0.0</IntranetIp>
    <Level>serious</Level>
    <EndTime>1543740301000</EndTime>
    <StartTime>1543740301000</StartTime>
    <SaleVersion>1</SaleVersion>
    <CanBeDealOnLine>false</CanBeDealOnLine>
    <InstanceName>server01</InstanceName>
  </SuspEvents>
</DescribeAlarmEventListResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"B5446AFA-58B6-41DC-80E6-E0382AC5A1F4",
	"SuspEvents":[
		{
			"Uuid":"47900178-885d-4fa4-9d77-XXXXXXXXXXXX",
			"Description":"黑客入侵服务器后，为了让恶意后门程序能持久化运行，黑客常常将恶意SHELL脚本写入crontab、systemd等计划任务。",
			"CanCancelFault":false,
			"InternetIp":"10.0.0.0",
			"SuspiciousEventCount":1,
			"AlarmUniqueInfo":"8df914418f4211fbf756efe7a6f40cbc",
			"AlarmEventName":"Linux计划任务执行异常指令",
			"AlarmEventType":"进程异常行为",
			"IntranetIp":"10.0.0.0",
			"Level":"serious",
			"EndTime":1543740301000,
			"StartTime":1543740301000,
			"CanBeDealOnLine":false,
			"SaleVersion":"1",
			"InstanceName":"server01"
		}
	],
	"PageInfo":{
		"Count":1,
		"TotalCount":1,
		"PageSize":10,
		"CurrentPage":1
	}
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/aegis)

