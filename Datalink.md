## 数据链通讯 （Datalink Communications）
### 前言
数据链通讯是现代民航发展的重要产物。现实中的民航数据链通讯系统是一套非常复杂的系统，由于篇幅限制，编写组无法在此进行详细介绍。我们将从最简单的角度出发，介绍现实中有关数据链通讯的背景和应用现状，让飞友对数据链通讯有一个大致的概念，然后再对如何在模拟飞行中使用数据链通讯进行介绍。

请注意，除非特殊说明，本篇中的所有情况均默认发生于中国大陆空域，所有技术规范和标准程序均采用中国民用航空局规定的标准，以中国民用航空局飞行标准司在2018年2月24日发布的咨询通告《使用数据链通讯系统的运行批准程序》作为主要参考文献。所有信息只用于模拟飞行时进行参考，编写组不对信息的真实性和可靠性作保证。
### 概念
在航空电信（Aeronautical Telecommunication）中，数据链（DataLink）是涵盖多种不同数据链系统和子网的统称。数据链通信（Data Link Communications）是用于发送和接收数据信息（digital information）的通信手段。数据链通信与语音通信（Voice Communications）是航空移动通信服务（Aeronautical MobileService）的组成部分。数据链服务（Data Link service）为保障空中交通管理安全与高效，提高空域容量提供通信支持手段。

数据链系统的主要架构如下图所示：

![image](https://user-images.githubusercontent.com/101052757/165099547-956b6a59-4abc-4a7d-82e3-1412c736351d.png)

一般来说，完整的数据链系统包含以下内容：

#### ATN （Aeronautical Telecommunication Network） 航空电信网 
不做详细介绍。
#### ACARS （Aircraft Communication Addressing and Reporting System） 飞机通信寻址与报告系统 
ACARS 是一种在飞机与地面站之间通过甚高频、高频或卫星通信手段传输简短报文的数据链系统。 

ARINC 公司于 1978 年设计了 ACARS 协议以期取代甚高频话音通信服务。随后 SITA 公司建设了更多地面站以增强其服务能力。航空公司于 20 世纪 80 年代开始使用 ACARS 以降低机组负荷、提高数据完好性。ACARS系统通常包含机载ACARS系统和地面ACARS系统两部分：
  + 机载 ACARS 系统包括 ACARS 管理单元（MU, Management Unit）的航电设备和控制显示单元（CDU, Control Display Unit）。
  + 地面 ACARS 系统由无线电地面站和传输网络组成。
 
ACARSATS 应用包括：
+ 放行许可（DCL, Departure Clearance）
+ 洋区放行许可（OCL, Oceanic Clearance）
+ 飞行机组终端气象服务（TWIP, Terminal Weather Information for Pilots）
+ 数字化自动航站情报服务 （ D-ATIS, Digital Automatic Terminal Information Service）

### 典型数据链应用
#### ADS-C （Automatic Dependent Surveillance-Contract） 合同式自动相关监视
ADS-C 自动将监视信息（位置等飞行数据）下发至管制单位的系统。当完成初始登录/通知（initial logon/notification）后，ADS-C将在飞机与地面站之间建立一个连接。在不需要飞行机组介入的情况下，洋区管制单位/运行控制单位可与飞机设立“合同”（contract），接收飞机的身份、位置、高度、马赫数、垂直变化率、航迹、磁航向、地速、导航点、气象数据等信息。 

#### CPDLC （Controller Pilot Data Link Communication） 管制员飞行机组数据链通信 
CPDLC 是使用数据链通信方式实现的管制员和飞行机组之间的空管通信手段。飞机下发至 ATSU 的报文可遵循标准格式或可为自由文本（freetext）。管制员发送的报文一般遵循标准格式并通常需要飞行机组做出回应。

作为CPDLC的一种特殊应用，我们介绍CPDLC-DCL。CPDLC-DCL（CPDLC-Departure Clearance Service）是在美国境内多个机场提供的离场放行许可服务。该服务使用 FANS 1/A(+)系统经由 VDL Mode 0/A 和（或）VDL Mode 2 子网提供。在这些提供CPDLC-DCL 的机场，可能会为未装备 FANS 系统的飞机提供 PDC 服务。CPDLC-DCL 提供了请求、发布初始和修订的离场放行许可（DCLs）的手段。CPDLC-DCL 报文包括离场程序、飞行计划航路、初始和请求高度、二次代码、离场频率和其它非航路信息。CPDLC-DCL 与国际通用 DCL 运行不同。国际通用 DCL 为 ACARSATCDCL 应用，由 ARINC 623/EUROCAE ED-85A 标准定义，而非 FANS CPDLC应用。当成功建立 ATC 连接，管制员批准 CPDLC-DCL 后，无需飞行机组请求放行许可，CPDLC-DCL 报文将自动发送至飞机。

#### PDC （Pre-Departure Clearance) 起飞前放行
PDC 是一种基于订阅方式的服务，可在滑行前高效提供文本形式的电子离场放行许可。管制放行许可通过数据链通信方式发送给订阅者的签派或运控中心，随后该放行许可经由互联网、登机口、航空公司运控终端、FBO（Fixed-Base Operator， 固定基地运营人）终端或 ACARS 传递给飞行机组。飞机不必须装备数据链通信航电设备即可使用 PDC 服务。

***PDC与 CPDLC-DCL 的根本区别在于 PDC 服务依赖于运营人通过第三方将 PDC 发送给飞机，而 CPDLC-DCL 服务则在登录/通知后直接在塔台自动化系统与飞机 FANS 航电系统之间建立直接连接。在中国大陆空域，机组申请数字化放行的步骤和CPDLC-DCL大致相同，但仍存在细微差别。因此在模拟飞行中，一般采用CPDLC-DCL的规范进行起飞前放行的发布，并且称其为DCL放行。***

下图为中国民用航空局于2012年发布的民航行业标准MH/T 4035-2012号《基于地空数据链的航空器起飞前放行服务》文件中规定的DCL 系统常规服务流程图。

![image](https://user-images.githubusercontent.com/101052757/165107955-f6e3b9a6-2b4d-45f6-8e32-ea679bbd9be7.png)

#### TDLS （Tower Data Link System） 塔台数据链系统 

TDLS 自动将塔台生成的信息通过数据链通信传送给飞机。TDLS 系统可为 CPDLC-DCL 和 PDC 提供链路。TDLS 系统与本地气象数据、飞行数据的接口可为飞行机组提供 PDC、D-ATIS 和 CPDLC-DCL 服务。 

### PBCS简介
#### PBCS的概念
国际民航组织（ICAO）规定：
> *The performance-based communication and surveillance (PBCS) concept provides objective operational criteria to evaluate different and emerging communication and surveillance technologies, intended for evolving air traffic management (ATM) operations. The PBCS also provides a framework in which all stakeholders (regulators, air traffic service providers, operators, communication service providers (CSP), and manufacturers) continue to collaborate in optimizing the use of available airspace while identifying and mitigating safety risks.*

> *基于性能的通信和监视（PBCS）概念提供了客观的操作标准，以评估不同的和新兴的通信和监视技术，旨在不断发展空中交通管理（ATM）业务。PBCS还提供了一个框架，所有利益相关者（监管者、空中交通服务提供商、运营商、通信服务提供商（CSP）和制造商）继续合作，优化现有空域的使用，同时识别和减少安全风险。*

#### PBCS和PBN的区别
> *The PBCS concept is aligned with that of performance-based navigation (PBN). While the PBN concept applies required navigation performance (RNP) and area navigation (RNAV) specifications to the navigation element, the PBCS concept applies required communication performance (RCP) and required surveillance performance (RSP) specifications to communication and surveillance elements, respectively. However, there are some differences between the PBCS and PBN concepts:*

> + *the PBCS concept applies RCP and RSP specifications, which allocate criteria to ATS provision, including communication services, aircraft capability, and the aircraft operator; whereas the PBN concept applies RNP/RNAV specifications, which allocate criteria only to the aircraft capability and the aircraft operator;* 

> + *the PBCS concept includes post-implementation monitoring programmes, on a local and regional basis, with global exchange of information; whereas the PBN concept includes real time monitoring and alerting functionality in the aircraft capability.* 

> *PBCS的概念与基于性能的导航(PBN)的概念是一致的。PBN概念将所需的导航性能（RNP）和区域导航（RNAV）规范应用于导航要素，而PBCS概念将所需的通信性能（RCP）和所需的监视性能（RSP）规范分别应用于通信和监视要素。然而，PBCS和PBN概念之间有一些区别。*

> + *PBCS 概念采用 RCP 和 RSP 规格，将标准分配给 ATS 的提供，包括通信服务、飞机能力和飞机操作员；而 PBN 概念采用 RNP/RNAV 规格，仅将标准分配给飞机能力和飞机操作员* 

> + *PBCS 概念包括在本地和区域基础上的实施后监测计划，并进行全球信息交流；而 PBN 概念包括飞机能力的实时监测和警报功能。* 



