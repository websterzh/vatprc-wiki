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

> + *PBCS 概念采用 RCP 和 RSP 规格，将标准分配给 ATS 的提供，包括通信服务、航空器能力和航空器驾驶员；而 PBN 概念采用 RNP/RNAV 规格，仅将标准分配给航空器能力和航空器驾驶员。* 

> + *PBCS 概念包括在本地和区域基础上的实施后监测计划，并进行全球信息交流；而 PBN 概念包括航空器能力的实时监测和警报功能。* 

#### 全球 PBCS 合作协议（ Global PBCS Charter）
在 PBCS 手册（ ICAO Doc 9869）和全球运行数据链手册（ GOLD，ICAO Doc 10037）中均规定： ANSP 和运营人应在其与 CSP 签订的服务合同中明确规定对 CSP 的 RCP/RSP 规范要求、数据链通信性能监测、数据链通信数据记录、故障报告等条款。因该要求涉及所有拟实施 PBCS 的 ANSP、运营人和 CSP，逐一对现有服务合同条款进行更新并重新签订需消耗极大的资源和成本。而且在某些区域需多个 CSP 协同解决。

基于上述原因， ICAO 运行数据链工作组（ OPDLWG）提出了各利益相关方共同签订全球 PBCS 合作协议（ Global PBCS Charter）的解决方案。签署了 PBCS Charter 的 ANSP、运营人和 CSP 等同于满足 ICAO Doc 9869 和 ICAO Doc 10037 中所规定 CSP 服务合同条款。

#### 全球PBCS实施情况
目前已知的全球计划PBCS区域包括：（均采用RCP240/RSP180规范）

+ 中国 *（L888 SANLI-XKC航段，Y1，Y2）*

+ 新加坡

+ 日本 *（Fukuoka FIR Oceanic Airspace）*

+ 印度尼西亚 *（Ujung Pandang FIR）*

+ 新西兰 *（Auckland Oceanic FIR）*

+ 美国 *（New York Oceanic East FIR）*

+ 北大西洋 NAT *（Santa Maria Oceanic FIR）*

+ 斯里兰卡 *（Colombo FIR）*

### 中国大陆地区提供 CPDLC/ADS-C 数据链服务的航路（现实中）
#### 数据链服务范围和规范
中国大陆飞行情报区内提供 CPDLC/ADS-C 数据链服务的空域/航路范围包括：**L888（KADKI-XKC 航段）、Y1、Y2。** 这些空域/航路的通信和监视手段，所需通信和/或监视性能规范，管制最低纵向间隔标准详见附件 A。相关管制单位 CPDLC/ADS-C 地面系统支持 FANS 1/A 应用。

#### ADS-C服务
略

#### CPDLC服务
以下为中国民用航空局规定的CPDLC使用规范和程序：

> *管制员/航空器驾驶员如果启动并使用 CPDLC，应当执行 ICAO PANS-ATM Doc4444（2016 年，第 16 版）（下同）第 14 章中相关规则、标准和程序。*

>*管制员/航空器驾驶员如果启动并使用 CPDLC，应当使用 ICAO PANS-ATM Doc4444 12.3.6 中CPDLC 用语。*

>*当开始使用 CPDLC 通信时，管制单位应通知航空器备用的 VHF 或 HF 话音频率。*

>*一旦 CPDLC 连通建立，航空器驾驶员应下发一个 CPDLC 位置报告。*

>*航空器驾驶员用以登录地面系统的识别标志必须与飞行计划相关项写的航空器识别标志一致。*

>*航空器驾驶员如果启动并使用 CPDLC，应当在收到 CPDLC 上行指令的 60 秒内完成回复，或者当飞行员需要额外的时间考虑如何回复指令时，应选择 STANDBY，不需要回复的指令除外。*

>*除紧急情况外，管制员或驾驶员通过 CPDLC 进行通信联络，通常应通过 CPDLC 回答。如管制员或驾驶员通过话音进行通信联络，通常应通过话音回答。无论何时，只要管制员认为有必要对通过 CPDLC拍发的电报进行更正或需要对电报内容加以澄清，管制员或驾驶员可以使用可供使用的最适当手段更正或者澄清指令/请求。使用话音通信对尚未收到运行答复的 CPDLC 电报进行更正时，管制员或驾驶员的通话之前须加用语“CPDLC（电报类型）作废”，后接正确的管制指令或者请求。*

>*航空器从一个不提供 CPDLC 服务的区域，飞入提供（或备份）有 CPDLC 服务的区域，航空器驾驶员必须在预计进入 CPDLC 区域前 15 分钟，人工登录到地面系统。*

>*在同时提供 CPDLC 服务的管制区之间飞行时，除非地面管制单位要求，接受 CPDLC 服务的航空器在从一个管制区飞入另一个提供 CPDLC 服务的管制区时，一般不需要人工登录到下一个地面系统。向下一个地面系统进行登录的工作，由正在为航空器提供服务的管制单位在航空器进入下一个区域前完成，而不需要飞行机组的干预。*

>*移交 CPDLC 服务时，话音通信和 CPDLC 的移交须同时进行。当一架航空器被从能提供 CPDLC的管制单位移交给不能提供 CPDLC 的管制单位时，CPDLC 的终止须和话音通信的移交同时进行。*

>*管制员对有待答复的上行电文尚未收到飞行员的答复就决定移交航空器的，该管制员应该换用话音通信以澄清与未复电文有关的任何疑问。*

#### 中国大陆地区数据链服务航路情况说明
![image](https://user-images.githubusercontent.com/101052757/165226823-fcd16404-00ce-49bd-8f2e-ba69530412d4.png)
