# DescribeSuspEvents {#doc_api_1030372 .reference}

查询异常事件列表。

告警事件分为告警与异常两个维度，一个告警事件包含多个异常事件。此API可以获取异常事件的列表。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=aegis&api=DescribeSuspEvents)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeSuspEvents|系统规定参数。取值：DescribeSuspEvents。

 |
|AlarmUniqueInfo|String|否|8df914418f4211fbf756efe7a6f40cbc|告警事件的唯一标识。

 |
|CurrentPage|String|否|1|当前页码。

 |
|Dealed|String|否|Y|异常事件状态：

 -   N：待处理告警
-   Y：已处理告警

 |
|From|String|否|sas|请求来源标识，固定为aqs。

 |
|Lang|String|否|zh|异常事件的语言类型：

 -   zh：中文
-   cn：英文

 |
|Levels|String|否|serious,suspicious,remind|告警事件的危险等级，多个逗号分隔。以下危险等级严重程度依次递减：

 -   serious：紧急
-   suspicious：可疑
-   remind：提醒

 |
|Name|String|否|挖矿|异常事件名称或者主机名称，支持模糊匹配。

 |
|PageSize|String|否|10|分页查询时设置的每页行数。默认值为20。

 |
|ParentEventTypes|String|否|网站后门|异常事件分类名称。

 |
|Remark|String|否|8.8.8.8|主机IP地址或者名称。

 |
|SourceIp|String|否|2.2.2.2|接口访问者源IP。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Count|Integer|10|当前返回结果数量。

 |
|CurrentPage|Integer|1|当前页。

 |
|PageSize|Integer|20|每页显示告警的条数。

 |
|RequestId|String|0C7FAD74-83FA-4671-9250-A5F2A64F437A|请求ID。

 |
|SuspEvents| | |异常事件列表。

 |
|└AlarmEventName|String|Linux计划任务执行异常指令|告警事件名称。

 |
|└AlarmEventType|String|进程异常行为|告警事件类型。

 |
|└AlarmUniqueInfo|String|8df914418f4211fbf756efe7a6f40cbc|告警事件的唯一标识。

 |
|└CanBeDealOnLine|Boolean|true|能否在线处理。

 |
|└DataSource|String|N/A|忽略该字段。

 |
|└Desc|String|webshell|影响概况描述。

 |
|└EventStatus|Integer|1|告警事件的状态：

 -   PENDING（1：待处理）
-   IGNORE（2： 已忽略）
-   HANDLED（4： 已确认）
-   FAULT（8： 已标记误报）
-   DEALING（16： 处理中）
-   DONE（32： 处理完毕）
-   EXPIRE（64： 已经过期）

 |
|└EventSubType|String|XorDDoS木马|异常事件名称。

 |
|└Id|Long|1000|唯一标识。

 |
|└InstanceName|String|nginx|关联实例的名称。

 |
|└InternetIp|String|103.1.1.33|关联实例的公网IP。

 |
|└IntranetIp|String|10.1.1.109|关联实例的私网IP。

 |
|└LastTime|String|2018-09-26 01:51:01|事件发生时间。

 |
|└Level|String|serious,suspicious,remind|告警事件的危险等级：

 -   serious：紧急
-   suspicious：可疑
-   remind：提醒

 |
|└Name|String|恶意进程（云查杀）-XorDDoS木马|异常事件的完整名称。

 |
|└OccurrenceTime|String|2018-09-26 01:51:01|操作备注消息。

 |
|└OperateMsg|String|success|操作备注消息。

 |
|└SaleVersion|String|1|需要的售卖版本：

 -   0：基础版本
-   1：企业版本

 |
|└Uuid|String|bf6b30d3-eea8-4924-9f0a-XXXXXXXXXXXX|关联实例的唯一标识。

 |
|TotalCount|Integer|100|查询总数量。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

/?AlarmUniqueInfo=8df914418f4211fbf756efe7a6f40cbc
&CurrentPage=1
&Dealed=Y
&From=sas
&Lang=zh
&Levels=serious,suspicious,remind
&Name=挖矿
&PageSize=10
&ParentEventTypes=网站后门
&Remark=8.8.8.8
&SourceIp=2.2.2.2
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeSuspEventsResponse>
  <TotalCount>3</TotalCount>
  <Count>2</Count>
  <PageSize>20</PageSize>
  <RequestId>0C7FAD74-83FA-4671-9250-A5F2A64F437A</RequestId>
  <CurrentPage>1</CurrentPage>
  <SuspEvents>
    <EventStatus>1</EventStatus>
    <SaleVersion>1</SaleVersion>
    <IntranetIp>10.0.0.0</IntranetIp>
    <EventSubType>XorDDoS木马</EventSubType>
    <Name>恶意进程（云查杀）-XorDDoS木马</Name>
    <DataSource>aegis_suspicious_event</DataSource>
    <OccurrenceTime>2018-09-26 01:51:01</OccurrenceTime>
    <InstanceName>server01</InstanceName>
    <Desc>XORDDoS木马入侵后，会在Linux的定时任务中植入恶意代码。</Desc>
    <CanBeDealOnLine>false</CanBeDealOnLine>
    <Uuid>bf6b30d3-eea8-4924-9f0a-XXXXXXXXXXXX</Uuid>
    <InternetIp>10.10.1.1</InternetIp>
    <Level>serious</Level>
    <Id>3682</Id>
    <LastTime>2018-10-24 21:06:01</LastTime>
  </SuspEvents>
  <SuspEvents>
    <EventStatus>1</EventStatus>
    <SaleVersion>1</SaleVersion>
    <IntranetIp>10.0.0.0</IntranetIp>
    <EventSubType>XorDDoS木马</EventSubType>
    <Name>恶意进程（云查杀）-XorDDoS木马</Name>
    <DataSource>aegis_suspicious_event</DataSource>
    <OccurrenceTime>2018-09-26 02:01:01</OccurrenceTime>
    <InstanceName>server01</InstanceName>
    <Desc>XORDDoS木马入侵后，会在Linux的定时任务中植入恶意代码。</Desc>
    <CanBeDealOnLine>false</CanBeDealOnLine>
    <Uuid>bf6b30d3-eea8-4924-9f0a-XXXXXXXXXXXX</Uuid>
    <InternetIp>10.10.1.1</InternetIp>
    <Level>serious</Level>
    <Id>3683</Id>
    <LastTime>2018-10-24 21:01:01</LastTime>
  </SuspEvents>
</DescribeSuspEventsResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Count":2,
	"TotalCount":3,
	"PageSize":20,
	"RequestId":"0C7FAD74-83FA-4671-9250-A5F2A64F437A",
	"SuspEvents":[
		{
			"Uuid":"bf6b30d3-eea8-4924-9f0a-XXXXXXXXXXXX",
			"EventStatus":1,
			"LastTime":"2018-10-24 21:06:01",
			"InternetIp":"10.10.1.1",
			"Name":"恶意进程（云查杀）-XorDDoS木马",
			"DataSource":"aegis_suspicious_event",
			"OccurrenceTime":"2018-09-26 01:51:01",
			"IntranetIp":"10.0.0.0",
			"Id":3682,
			"Level":"serious",
			"SaleVersion":"1",
			"CanBeDealOnLine":false,
			"InstanceName":"server01",
			"Desc":"XORDDoS木马入侵后，会在Linux的定时任务中植入恶意代码。",
			"EventSubType":"XorDDoS木马"
		},
		{
			"Uuid":"bf6b30d3-eea8-4924-9f0a-XXXXXXXXXXXX",
			"EventStatus":1,
			"LastTime":"2018-10-24 21:01:01",
			"InternetIp":"10.10.1.1",
			"Name":"恶意进程（云查杀）-XorDDoS木马",
			"DataSource":"aegis_suspicious_event",
			"OccurrenceTime":"2018-09-26 02:01:01",
			"IntranetIp":"10.0.0.0",
			"Id":3683,
			"Level":"serious",
			"SaleVersion":"1",
			"CanBeDealOnLine":false,
			"InstanceName":"server01",
			"Desc":"XORDDoS木马入侵后，会在Linux的定时任务中植入恶意代码。",
			"EventSubType":"XorDDoS木马"
		}
	],
	"CurrentPage":1
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/aegis)

