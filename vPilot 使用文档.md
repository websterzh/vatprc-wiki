# vPilot 使用文档

本文档翻译自 [vPilot 官方文档](https://vpilot.rosscarlson.dev/Documentation)。

本文内容仅供参考，随着时间推移可能会有部分内容落后于官方文档，请以最新的官方文档为准。

## 目录

- [系统要求](#系统要求)
- [安装](#安装)
- [启动 vPilot](#启动-vpilot)
- [配置](#配置)
- [模型匹配](#模型匹配)
- [创建客制化模型匹配规则](#创建客制化模型匹配规则)
- [模型匹配规则介绍](#模型匹配规则介绍)
- [连接到 VATSIM](#连接到-vatsim)
- [设置应答机](#设置应答机)
- [与管制员沟通](#与管制员沟通)
- [SELCAL](#selcal)
- [请求管制员信息（获取文字ATIS）](#请求管制员信息获取文字atis)
- [提交飞行计划](#提交飞行计划)
- [私信信息](#私信信息)
- [. 命令](#-命令)
- [断开与 VATSIM 的连接](#断开与-vatsim-的连接)
- [下载更新](#下载更新)
- [远程运行vPilot](#远程运行vpilot)
- [共享驾驶舱（Observer）模式](#共享驾驶舱observer模式)
- [常见问题](#常见问题)
- [获取帮助](#获取帮助)
- [vPilot 最终用户许可协议](https://vpilot.rosscarlson.dev/vPilotEULA.txt)

## 系统要求

- 操作系统：Microsoft Windows 7, Windows 8.1 或 Windows 10
- 运行库：Microsoft .NET Framework 4.7.2
- 磁盘空间：在存储应用程序数据和用户文档的盘上 100 MB 的可用空间
- 支持的模拟器：
  - Microsoft Flight Simulator X with Acceleration or Service Pack 2 (FSX)
  - Microsoft Flight Simulator X Steam Edition (FSX:SE)
  - Lockheed Martin Prepar3D (P3D)
  - Microsoft Flight Simulator (MSFS 2020)

## 安装

下载 vPilot 后，双击下载的文件开始安装。 默认情况下，您无需更改安装路径，以免出现文件权限问题。 如果您更改安装文件夹，请务必指定一个不需要管理员权限的文件夹，以便 vPilot 能够写入其配置文件。

安装完成后，您可以选择启动 vPilot。

## 启动 vPilot

您可以双击vPilot桌面快捷方式（如有）或在程序列表中找到 vPilot 并启动它。 vPilot会在模拟器外部运行，而不像其他一些插件那样需要从模拟器内的菜单启动。

第一次运行 vPilot 时，您将看到一个窗口弹出，该消息表明您尚未完全配置 vPilot，单击 `是(Y)` 打开设置窗口并配置 vPilot。

![QQ图片20220424160545](https://user-images.githubusercontent.com/104274235/165445007-3ed5e4ca-35f1-4872-a407-b37263f78945.png)

vPilot 启动后，它会立即尝试通过 SimConnect 连接到模拟器 。 如果模拟器尚未运行，它将每隔 10 秒重试一次。当最终建立与模拟器的连接时，vPilot会在主消息区域显示一条消息（以 Lockheed Martin Prepar3D v5为例）。

![QQ图片20220425135712](https://user-images.githubusercontent.com/104274235/165033579-de11e382-795c-4cf5-a2fc-ffdb2ddfac0c.png)


## 配置

要配置 vPilot，请单击 Settings 按钮。 您将看到如图所示的画面。
### Network

![QQ图片20220425144724](https://user-images.githubusercontent.com/104274235/165035373-6e173d09-fe32-437a-8899-5c2920594bb9.png)

在本页，您只需输入您的 VATSIM CID/密码、注册名和您的家乡机场，并且选择要连接的 VATSIM 服务器。所有的VATSIM连飞服务器都是互通的，所以您只需要选择在您网络环境下连接最稳定的服务器。

### Notifications

![QQ图片20220425144731](https://user-images.githubusercontent.com/104274235/165035406-179ef622-ea14-4beb-8b89-9f3214e06517.png)

此选项卡可以选择当 vPilot 不在最前端时，哪些情况会使vPilot任务栏的图标闪烁。

|vPilot 选项   |中文注释   |
| :------------------ | ------------------------------------------------------------ |
| Flash taskbar icon for new private message       |       收到新的私信时任务栏闪烁 |
| Flash taskbar icon for text radio message            |   收到新的无线电文字消息时任务栏闪烁 |
| Flash taskbar icon for SELCAL message                |   收到新的SELCAL消息时任务栏闪烁 |
| Flash taskbar icon when disconnected from network   |    vPilot 与 VATSIM连接断开时任务栏闪烁 |
| Show incoming text messages in simulator          |      在模拟器中显示 vPilot 的文字消息（强烈建议文字机组开启本选项卡，该选项卡能够提高您的指令执行速度） |

### Fonts

![QQ图片20220425144737](https://user-images.githubusercontent.com/104274235/165035510-1633255d-2cc5-4da7-b1c5-5e9e713e8175.png)

字体选项卡用于选择管制列表与文本消息的字体。
### Audio

![QQ图片20220425144743](https://user-images.githubusercontent.com/104274235/165035543-58267466-866d-48cf-b564-0561be237d7b.png)

在这里，您可以选择您希望使用的输入设备（麦克风），以及输出设备（如：音响、耳机）。 如果设备尚未插入，您需要关闭 `settings` 窗口，插入设备，然后重新打开 `settings` 窗口。

选择音频输出设备后，调整音量滑块，使音量处于自己听起来舒适的区域。部分机模可以使用其无线电通信面板的接收旋钮调节音量，例如 Flightsimlabs320 系列。

选择麦克风设备后，调整麦克风音量滑块，同时以正常声音讲话，使音量大部分处于绿色区域。这将有助于确保您可以被网络上的其他飞行员和管制员清楚地听到。 **注意：若您音量设置的过高，可能会导致其他飞行员或管制员听力受损。**

如果您选中 `Disable realistic ATC audio effects` 的框，则传入的声音将不会有 VHF 无线电噪音。 通常，为了使音频真实不会选中此框。 但是，如果您很难理解 ATC 所说的内容，选中此框可能会对您有所帮助。

如果您选中 `Disable HF background noise` 的框，则传入的声音将不会有 HF（高频） 无线电噪音。 通常，为了使音频真实不会选中此框。 但是，由于HF（高频）无线电的特性，可能会出现背景噪音远大于其他机组或管制员的声音的情况（例如在北大西洋飞行时）。所以当您很难理解或听清ATC所说的内容时，选中此框可能会对您有所帮助。
### Push-To-Talk (PTT)

![QQ图片20220425144749](https://user-images.githubusercontent.com/104274235/165035597-e20804ea-1308-44c1-8d34-0d58fec154f3.png)

在此部分，您可以选择要用于 PTT 的键盘键或操纵杆/按钮。 只需按下标有 `Set new PTT Key or Button` 的按钮，然后在键盘键或操纵杆上按下要用于 PTT 的按键/按钮。 vPilot 将检测并相应地更新 `Current PTT Assignment` 的映射。

请注意，如果您的PTT使用的时键盘按键，当您以管理员身份运行 FSX/P3D/MSFS时，必须同样以管理员身份运行 vPilot 才可以保证vPilot正确识别该按键。

如果您不想在 VATSIM 上使用语音，请按 `Clear Current PTT Assignment` 按钮将PTT的映射删除。
### The Model Matching Tabs

![QQ图片20220425144756](https://user-images.githubusercontent.com/104274235/165035677-bdb72f14-e844-407d-8317-6c4b28dd04e8.png)

有关模型匹配如何在 vPilot 中工作的更多信息，请参阅下面的[模型匹配](#模型匹配)部分。 对于在您系统上每个受支持的模拟器，您将拥有一个选项卡。
#### The Model Matching - Advanced

![QQ图片20220425144809](https://user-images.githubusercontent.com/104274235/165035703-432a1485-6d67-434e-8818-56b6a94cf4ef.png)

此部分允许您在模型匹配中排除模型（单独或作为整个文件夹）。 您还可以通过使用 `Move Up` 和 `Move Down` 按钮在此列表中重新排列文件夹来确定文件夹的优先级。 vPilot 将首先搜索列表中较高的文件夹用于显示您在 VATSIM 上飞行时遇到的飞机的模型。
#### The Model Matching - Custom Rules

![QQ图片20220425144815](https://user-images.githubusercontent.com/104274235/165035728-69c5373f-8923-4c51-9512-501270f4e9a1.png)

在这里，您可以通过从计算机硬盘加载文件来添加自定义模型匹配规则。 如果您创建了自己的文件，或者您从其他用户那里收到了文件，或者从您的 VA 网站下载了该文件，您可能会这样做。 自定义规则文件可以重新排序，以设置它们用于模型匹配的优先级。 当 vPilot 自动扫描您已安装的模型时，自定义规则始终优先于找到的模型。
### Performance

![QQ图片20220425144820](https://user-images.githubusercontent.com/104274235/165035751-7836d7a8-b35b-474e-b4e5-47660f8d0403.png)

在这里，您可以限制 vPilot 显示在您模拟器里的飞机数量。 如果您在航空器较多的区域发现帧率下降，你可以通过降低这个值来减少您模拟器中显示的航空器数量。
### Updates

![QQ图片20220425144824](https://user-images.githubusercontent.com/104274235/165035772-9837c121-c3e9-4f53-b26d-d924c5d7f7bc.png)

如果您勾选了 `Check for vPilot updates` ， vPilot 将会在每次启用时自动检查可用更新。 有关更新的详细信息，请参阅下载更新部分。 此选项应保持启用状态，以确保您知道何时发布新版本的 vPilot 。注：由于 Velocity 的实施，请确保您的 vPilot 版本已更新至 v3.x版本 ，否则将无法连接到 VATSIM连飞网络。

此选项卡还允许您选择从 `Stable` 还是 `Beta` 更新下载。 大多数用户应选择 `Stable` 。 如果您想获得最新可用的 vPilot 版本，您可以将此设置更改为 `Beta` ，但 vPilot 的 Beta 版本尚未经过彻底测试，可能存在BUG。
### Miscellaneous

![QQ图片20220425144830](https://user-images.githubusercontent.com/104274235/165035795-9d29283b-636d-4395-8eaa-095ed4b81ca2.png)

在这里，您可以选择让 vPilot 在您的飞机离地时自动开启应答机的C 模式。 如果您的飞机集成有 SquawkBox 转发器，则应不选中此复选框，因为 vPilot 将能够直接从飞机面板读取应答机模式。

勾选 `Keep window visible` 可以将您的 vPilot 主窗口保持在其他窗口前端。 请注意，当 FSX 在全屏模式下运行时，这个功能将不起作用。

## 模型匹配

自2.0版以来，vPilot的模型匹配功能相较之前的版本已经发生了质的改变--更加的自动化了。vPilot 2.0会自动检测您电脑中已经安装的模拟器，从您模拟器的相关配置文件中找到已安装的AI机模/涂装的位置，并从中获取这些AI机模/涂装的相关信息。之后，vPilot会将获取到的信息与vPilot服务器内的已知数据库进行比对，从而确定您电脑中的哪些AI机模/涂装可以作为您连飞时对于其他航空器的模型匹配。

vPilot在扫描您本地AI机模/涂装的期间，如果发现了不存在于已知数据库中的航空器类型，vPilot将会尝试使用该机模/涂装Aircraft.cfg文件内的信息去定义这个机模/涂装的类型。

vPilot在您每次启动它时，都会自动检测您是否安装了新的机模/涂装，以决定是否需要重新对您本地的AI机模/涂装进行上述的扫描。

当您在VATSIM连飞期间，vPilot会在您遇到其他机组时，从扫描结果中选择一个最合适的AI机涂装对该机组的航空器进行匹配。如果您本地AI机模中没有可以与之相匹配的涂装，vPilot则会使用预设好的缺省涂装进行匹配。如果需要修改缺省涂装，您可以在 `Settings` > `Model Matching` 选项卡内的 `缺省涂装`(`Default Model`)  文本框输入您希望使用的缺省涂装。

![image](https://user-images.githubusercontent.com/25072307/165121408-0afbf266-c1b3-45cb-8336-01bc8be5af8a.png)

例如，您希望使用FSX自带的塞斯纳172的蓝金色涂装作为机模匹配的缺省涂装，则只需要在文本框内输入“Cessna Skyhawk 172SP Paint1”。您输入的内容必须要与该机模Aircraft.cfg文件内相应涂装的`title`一致，如下所示：

*该机模/涂装的Aircraft.cfg文件可以在`SimObjects\Airplanes\C172`目录下找到。*

>[fltsim.0]  
>title=Cessna Skyhawk 172SP Paint1  
>sim=Cessna172SP  
>model=  
>panel=  
>sound=  
>texture=1  
>kb_checklists=Cessna172SP_check  
>kb_reference=Cessna172SP_ref  
>atc_id=G-BAFM  
>ui_manufacturer="Cessna"  
>ui_type="C172SP Skyhawk"  
>ui_variation=" Blue, Gold"  
>ui_typerole="Single Engine Prop"  
>ui_createdby="Microsoft Corporation"  
>description="A stable and trustworthy plane, most pilots...

## 创建客制化模型匹配规则

除了上述的自动匹配功能外，vPilot还给您提供了一个可供您使用vPilot数据库内不包含的航空器（例如匹配虚拟航空的涂装时），或客制化每个航空器所被匹配机模/涂装的方法。

您可以在`Settings` > `Model Matching` > `Custom Rules` 页面点击 `Add Custom Rule Set(s)` 按钮，加载您的客制化模型匹配规则。您可以手动创建规则文件，也可以从网络上下载。

如果您选择自己创建规则文件，您需要根据下面的模板创建一个XML文件：

```xml
<?xml version="1.0" encoding="utf-8"?>
<ModelMatchRuleSet>
</ModelMatchRuleSet>
```

并在第二行与第三行之间写入您的客制化模型匹配规则。

规则文件的格式见下文。

## 模型匹配规则介绍

下面是一段来自Ultimate Traffic 2的匹配规则：

```xml
<ModelMatchRule CallsignPrefix="BAW" TypeCode="B733" ModelName="F1UT2_733.BA.BA" />
<ModelMatchRule CallsignPrefix="COA" TypeCode="B733" ModelName="F1UT2_733.CO.CO" />
<ModelMatchRule CallsignPrefix="UAL" TypeCode="B733" ModelName="F1UT2_733.UA.UA" />
<ModelMatchRule CallsignPrefix="AWE" TypeCode="B733" ModelName="F1UT2_733.US.US" />
```

以上每一条规则都包含一个 `CallsignPrefix`（呼号前缀） 、 `TypeCode`（航空器机型） 以及 `ModelName` （涂装名）。当在连线过程中遇到了新的航空器时，vPilot会逐行扫描您添加的所有规则文件，直到找到与其相匹配的规则。只有当下列两个条件全部满足时，才会被认定为匹配：
>该航空器呼号的开头与 `CallsignPrefix` 所定义的值完全匹配。  
>该航空器的类型也与 `TypeCode` 所定义的值完全匹配时。  

随后，vPilot会将该航空器显示为这条规则中 `ModelName` 所定义的涂装。`ModelName` 的值应与该涂装在Aircraft.cfg文件内 `title` 的值一致。  
&nbsp;

除了定义呼号前缀(CallsignPrefix)以外，还可以定义以完整呼号(Callsign)为前提的规则，用来准确的定义一个特定的呼号所被匹配的涂装。在这种规则下，航空器的呼号必须完全匹配 `Callsign` 所定义的值才可以被匹配。这对于那些每个成员都拥有一个专属涂装的虚航来说是一个很实用的功能。  
&nbsp;

对用于匹配非航司的航空器（如通用航空）的规则，您可以将 `CallsignPrefix` 的值留空或完全去掉这一项。这样一来，vPilot就只会通过 `TypeCode` 对航空器进行匹配。假如您希望所有的C172都使用同一个AI机模的涂装进行匹配，则达到这个要求的规则如下：
```xml
<ModelMatchRule TypeCode="C172" ModelName="Cessna Skyhawk 172SP" />
```
&nbsp;

您也可以通过在 `ModelName` 中添加多个涂装名对满足匹配条件的航空器进行匹配。这种情况下，vPilot会**随机**选择您所定义的涂装之一对该航空器进行模型匹配。这个功能在匹配那些在某个特定机队有多种不同涂装的航空公司时很实用（例如JetBlue以及Frontier）。定义这种规则时，每个涂装名之间必须使用 `//`进行分隔。下面是一个来自MyTraffic3D为JetBlue所作的一条规则：
```xml
<ModelMatchRule CallsignPrefix="JBU" TypeCode="A320" ModelName="A320 MyPaint52//A320 MyPaint82//A320 MyPaint119//A320 MyPaint120" />
```
&nbsp;

这个功能同样适用于那些不需要对呼号进行匹配的规则。下面是一个FSX的默认匹配规则中的例子：
```xml
<ModelMatchRule TypeCode="C172" ModelName="Cessna Skyhawk 172SP//Cessna Skyhawk 172SP Paint1//Cessna Skyhawk 172SP Paint2//Cessna Skyhawk 172SP Paint3//Cessna Skyhawk 172SP Paint4//Cessna Skyhawk 172SP G1000" />
```

这条规则会不考虑呼号，随机将其中一个涂装匹配到任意一个遇到的C172上。  
&nbsp;

客制化的规则还可以通过航班号对执行代码共享航班的航空器进行匹配。下面的例子为Delta Connection和United Express在为SkyWest执飞代码共享航班时的匹配规则。
```xml
<ModelMatchRule CallsignPrefix="SKW" FlightNumberRange="4439-4858" TypeCode="CRJ2" ModelName="AIM CRJ200_Delta Connection_Skywest" />
<ModelMatchRule CallsignPrefix="SKW" FlightNumberRange="9780-9784" TypeCode="CRJ2" ModelName="AIM CRJ200_Delta Connection_Skywest" />
<ModelMatchRule CallsignPrefix="SKW" FlightNumberRange="4965-4974" TypeCode="CRJ2" ModelName="AIM CRJ200_ual skwywest nc" />
<ModelMatchRule CallsignPrefix="SKW" FlightNumberRange="5156-5269" TypeCode="CRJ2" ModelName="AIM CRJ200_ual skwywest nc" />
<ModelMatchRule CallsignPrefix="SKW" FlightNumberRange="5480-5659" TypeCode="CRJ2" ModelName="AIM CRJ200_ual skwywest nc" />
<ModelMatchRule CallsignPrefix="SKW" FlightNumberRange="6190-6539" TypeCode="CRJ2" ModelName="AIM CRJ200_ual skwywest nc" />
```

从中可以发现，您可以通过多条规则来定义不同的航班号区间应当如何匹配。
&nbsp;

在您每次启动vPilot时，它还会从服务器下载一个记录了相似机型的数据库。这个数据库里包含了那些外形相近的机型及其机型代码。当vPilot在对航空器进行匹配时，如果该航空器的代码没有在规则中被写出，vPilot则会根据这个数据库选择一个使用与其相似机型的规则对它进行匹配。

例如：当您遇见一架呼号为“DAL123”的B733时，并且规则表中没有同时满足其呼号前缀和机型的规则，vPilot将会检查规则表中是否含有呼号前缀为“DAL”，以及机型为“B732”或“B734”的规则。
&nbsp;

以下为vPilot在对于规则表进行搜索的逻辑步骤：
1. 忽略所有未定义 `CallsignPrefix` 或 `Callsign` 的规则，并在余下的规则中寻找与该航空器 `CallsignPrefix`（呼号前缀） 或 `Callsign`（呼号） 完全匹配，且与其 `TypeCode`（机型） 完全匹配的规则。
2. 忽略所有未定义 `CallsignPrefix` 或 `Callsign` 的规则，并在余下的规则中寻找与该航空器 `CallsignPrefix`（呼号前缀） 或 `Callsign`（呼号） 完全匹配，且与其 `TypeCode`（机型） 相似的规则。
3. 忽略所有定义了 `CallsignPrefix` 或 `Callsign` 的规则，并在余下的规则中寻找与该航空器 `TypeCode`（机型） 完全匹配的规则。
4. 忽略所有定义了 `CallsignPrefix` 或 `Callsign` 的规则，并在余下的规则中寻找与该航空器 `TypeCode`（机型） 相似的规则。
&nbsp;

以上面提到的DAL123为例：
vPilot在进行第一步的过程中，会首先寻找 `CallsignPrefix` 为“DAL”（或 `Callsign` 为“DAL123”），以及 `TypeCode` 为“B733”的规则；  
如果没有匹配的规则，vPilot则会进行第二步，即寻找 `CallsignPrefix` 为“DAL”（或 `Callsign` 为“DAL123”），以及 `TypeCode` 与“B733”相似的规则，例如“B732”或“B734”；  
如果还是没有匹配，则会进行第三步，即在所有未定义 `CallsignPrefix` 或 `Callsign` 的规则中寻找一个 `TypeCode` 为“B733”的规则；  
如果依旧没有匹配，则会进行第四步，即在所有未定义 `CallsignPrefix` 或 `Callsign` 的规则中寻找一个 `TypeCode` 与“B733”相似的规则；  
如果最终也没有找到相匹配的规则，vPilot将会使用之前所定义的缺省涂装对该航空器进行模型匹配。

## 连接到 VATSIM

要连接到 VATSIM ，请单击 `Connect` 按钮。 此时，vPilot将会弹出 `Connect` 对话框。您需要在这里输入您的呼号以及机型ICAO代码，并输入您希望使用的SELCAL代码或留空。

![QQ图片20220425144516](https://user-images.githubusercontent.com/104274235/165035208-c064313e-a983-4f38-a7ed-779f31434456.png)

当您准备好接入 VATSIM 时，按下 `Connect` 按钮。 如果连接成功，您将在主消息区域看到一条连接成功的消息， 并且`Connect` 按钮将呈绿色亮起，并显示为 `Disconnect` 。 如果您所在位置范围内有管制员在线，他们的呼号及频率将出现在管制员列表中，以便您联系相应的管制员。

有关使用共享驾驶舱/ shared cockpit mode（observer）模式的详细信息，请参见下文。

## 设置应答机

在 VATSIM 上飞行时，您需要将应答机在 Standby 模式和 C 模式之间切换。 C 模式在您进入开放跑道和空中时使用，开启 C 模式后管制员将能够在其范围内查看您的高度。如果由于机场运行要求，飞行器在地面移动时需要将应答机 C 模式，将在对应管制员的ATC info或通波中标注。

**译者注：由于上述说明与VATSIM Code of Conduct（下称CoC）中的[B4](/../master/COC_translate_full.md#b4)项产生冲突，请机组依照CoC中的规定，在航空器运动过程中启用应答机的C模式（除非管制员要求将应答机调至Standby）。**

您可以通过三种方式使用 vPilot 设置应答机模式。
- 如果您所使用的机模插件集成了 SquawkBox 应答器，则当您在 模拟器 中的相应面别更改应答机模式时，vPilot 将会检测该变化。也是就，当 模拟器的应答机开启了 C 模式时，vPilot也会相应的将主窗口上的 `mode C` 按钮亮起。
- 如果您所使用的机模插件不支持 SquawkBox 集成，那么您需要手动在 vPilot 界面中，通过单击 `mode C` 按钮更改应答器模式。 `mode C` 按钮亮起时，表示应答机已经启用 C 模式，否则则表示应答机处于 Standby 模式。
- 最后一种方法是使用 模拟器 中的菜单栏的 Add-ons 。当 vPilot 运行时，此菜单中会出现 `Squawk Mode C` 或 `Squawk Standby` 选项。

这三个选项也适用于 squawk ident。当您第一次联系某个频率时，管制员可能会要求您 应答机识别 。这会使您在管制员的雷达上以不同的方式被显示出来，以便于管制员找到您的位置。如果您被要求 应答机识别，您可以单击飞机面板上的 ident 按钮（如果飞机具有 SquawkBox 转发器集成），或者单击 vPilot 主窗口上的 Ident 按钮。您也可以单击 模拟器 菜单栏 Add-ons 中的 `Squawk Ident` 来实现此功能。当 vPilot 将 ident 信号发送到网络时，vPilot 主窗口上的 `Ident` 按钮将会亮起。

## 与管制员沟通

当您连接到 VATSIM 时，范围内的所有管制员的呼号和频率将显示在 vPilot 主窗口左侧的管制员列表中，并按管制员席位的类型分组。当您将鼠标悬停在条目上时，将会显示该管制员的姓名。

为了与管制员建立通讯，您需要在飞机的无线电面板中调整 `COM1` 或 `COM2` 无线电频率，同时激活无线电发送和接收开关。在 vPilot 主窗口的右上角，当该 COM 无线电激活发送和接收时，您将看到 `TX/RX` 变为白色。

如果您连接到语音服务器，那么频率将显示为蓝色。否则它们将会是白色。

![QQ图片20220425140134](https://user-images.githubusercontent.com/104274235/165034000-c90fba17-af49-4d97-a65c-d76af78748f8.png)

当接入语音且您在您所在的频率上发送或接收语音时，`TX/RX` 会亮起。

![QQ图片20220425141346](https://user-images.githubusercontent.com/104274235/165034041-08e4ff94-7be9-491e-9b94-ed5fae7ddcd4.png)

![QQ图片20220425141533](https://user-images.githubusercontent.com/104274235/165034056-e190bf0f-210b-47b2-9a7b-8bb230b61a72.png)

您可以用 `COM1` 上接入一个管制员频率，用 `COM2` 上接入另一个管制员频率，并且您可以同时连接到多个管制员频率，但一次只能在其中一个管制员频率发送音频。

![QQ图片20220425140306](https://user-images.githubusercontent.com/104274235/165033810-5867ee34-41f5-4928-b7dc-699d9828b8fb.png)

![QQ图片20220425140320](https://user-images.githubusercontent.com/104274235/165033835-76d083c1-39a2-453c-9e90-6a3b28b2e241.png)

如果要通过文字消息与管制员通信，请确保您已选定 vPilot 主窗口，在消息区域底部的文本栏中输入您的消息，然后按 回车键发送您的消息。您可以在任何 COM 频率内以文本形式发送您的消息。

**译者注：根据CoC中[A16](/../master/COC_translate_full.md#a16)条的相关规定，您不可以在任何公开频率进行私人聊天，也不可以使用航空应急频率121.500MHz。**

收到的的文本消息显示在主消息区域中。如果您正在收听多个 COM 频率，则每条文本消息前面都将会显示它的所属频率。

![QQ图片20220425143136](https://user-images.githubusercontent.com/104274235/165033786-aa707147-784e-42a8-bddc-66c5aafcdbbc.png)

如果接收的文本消息专门针对您，则会发出提示音并且消息以白色显示。针对其他飞行员（或特别针对任何人）的文本无线电消息将以灰色显示。

![QQ图片20220425143422](https://user-images.githubusercontent.com/104274235/165033769-114cd8a6-bbbe-49b3-a732-2c5e2ef1ab0e.png)

最后这很重要！！！您的航空器必须通电且在无线电面板激活收发按钮才能使通讯正常工作。如果您的航空电子设备未通电或者收发按钮未激活，则两个 COM 无线电的 TX 和 RX 灯将以灰色显示。

![QQ图片20220425143526](https://user-images.githubusercontent.com/104274235/165033742-cff5b8b5-3980-4ac0-a55c-0e7b010bb00d.png)

## SELCAL

如果您在接入 VATSIM 时输入了 SELCAL 代码，那么管制员可以使用该代码向您的飞机发送 SELCAL 提示音。 SELCAL主要使用在嘈杂的 HF 频率。 飞行员通常会调低音量，这样他就不会受到 HF 噪音的干扰，当管制员需要通过 HF 与他交流时，管制员会发送 SELCAL 提示音以引起他的注意。 VATSIM 不开设 HF 频率，但出于现实目的，会通过VHF模拟HF频率且海洋管制员仍将模拟 SELCAL 过程。

如果您收到管制员发送的 SELCAL 消息，vPilot 将发出提示音并在主消息区域显示一条消息  

## 请求管制员信息（获取文字ATIS）

![QQ图片20220425145502](https://user-images.githubusercontent.com/104274235/165036059-56aa034d-8d45-4c37-9e79-7779c0827be3.png)

VATSIM 上的每个管制员都有管制员信息，同时部分管制员在线的机场会有 ATIS。 要查看此信息，可以双击管制员列表中的管制员。 该信息将在主消息区域中以绿色文字显示。

您还可以使用 .atis 命令请求管制员信息。

## 提交飞行计划

要创建和提交飞行计划，请按 vPilot 主窗口上的 `Flight Plan` 。您将看到截图中显示的窗口。此表格将包含您在上一次飞行期间最后在表格上输入的文字。即使未连接到 VATSIM 网络，您也可以填写表格，但在连接之前您将无法提交飞行计划。

如果您选中 `Heavy Aircraft` 复选框，vPilot 将在您的飞机类型代码前加上 `H/` ，以向管制员表明您正在驾驶尾流等级为重型的航空器。

您需要在 `Equipment Suffix` 中选择的您飞机的设备代码。请务必选择正确的设备后缀，以便管制员知道您可以接受哪种类型的导航指令。如果您不知道您飞机的设备代码，你可以参考[此处] ***（论坛更新后加入1554Equipment帖子超链接）***。

请务必选择正确的 `Voice` 选项。根据您的选择，vPilot 将在您的飞行计划备注中添加标签，以告知管制员您是否具有语音功能。

按 `Load` 或 `Save` 可以以 vPilot 或 SquawkBox 格式加载或保存飞行计划。

![QQ图片20220425144648](https://user-images.githubusercontent.com/104274235/165035333-330b30c7-a233-4971-b31e-2fc7878d9e44.png)

如果您已经提前在 VATSIM [网页](https://my.vatsim.net/pilots/flightplan)为您的呼号提交了飞行计划，您可以通过按 `Fetch From Server` 下载它。

以下为 `Flight Plan` 界面的中文释义：
| 界面原文       | 中文释义             |
| -------------- | -------------------- |
| Flight Type    | 飞行规则             |
| Departure      | 出发机场             |
| Destination    | 目的地机场           |
| Alternate      | 备降机场             |
| Departure Time | 离港时间             |
| Time Enroute   | 航路飞行时间         |
| Fuel Available | 可用燃油飞行时间     |
| Cruise Speed   | 巡航速度（真空速） |
| Heavy Aircraft | 重型飞机             |
| Equipment      | 设备代码             |
| Route          | 航路                 |
| Remarks        | 备注                 |
| Voice          | 通讯方式             |

以下为三种 `Voice` 方式的释义：
| 通讯方式     | 代码 | 描述                                     |
| ------------ | ---- | ---------------------------------------- |
| Voice        | /v/  | 可以接受语音管制并通过语音回复           |
| Receive Only | /r/  | 可以接受语音管制服务，但只能通过文字回复 |
| Text Only    | /t/  | 只能接受文字管制                         |
## 私信信息

在您使用 VATSIM 的飞行过程中，您可能会想要通过私信联系其他用户飞行员或管制员，或者他们可能通过私信与您联系。当您收到新的私信时， vPilot 将会添加一个选项卡，显示发送人的呼号，并浅蓝色突出显示。当您单击该选项卡时，将切换聊天的消息区域并显示私信内容，并且选项卡文本将变为浅灰色。聊天消息的第一行将会显示用户的连线姓名。如果在选项卡关闭后再次收到该用户新消息，呼号将再次以浅蓝色显示。

如果您要回复私信，请在聊天选项卡底部的命令行中输入您的消息，然后按下回车键。您发送的消息将以浅灰色显示，收到的消息将以浅蓝色显示。

您可以通过右击管制员列表中的管制员然后点击 `Open Private Chat` 来开启私信。这将创建一个新选项卡（或切换到现有选项卡，如果有），然后您可以输入您的私信。***但是切记，所有管制员指令因在 `com1` 或 `com2` 中发送回复，不得在私信窗口回复，频率堵塞或机模调频失败等情况例外***

您还可以使用 .chat 命令发起私信。有关详细信息，请参阅有关[点命令](#. 命令)的部分。

## . 命令

vPilot 支持以下 `.` 命令，可以在主消息区域下方的命令行或任何私信选项卡的底部输入这些命令：
| 命令                        | 描述                                                         | 示例                            |
| --------------------------- | ------------------------------------------------------------ | ------------------------------- |
| .chat 呼号                  | 打开一个指定呼号的新私信选项卡（或切换到现有选项卡）。       | .chat CCA081/.chat ZSHC_TWR     |
| .close                      | 关闭当前聊私信选项卡。                                       |                                 |
| .atis 呼号                  | 请求指定呼号的管制员信息或机场ATIS。                         | .atis ZSHC_TWR/.atis ZSHC_ATIS  |
| .msg 呼号 消息内容          | 将指定的私信内容发送到指定的呼号。                           | .msg CCA081 Hi/.msg ZSHC_TWR Hi |
| .wx 机场ICAO代码            | 请求机场 ID 的天气（METAR）。                                | .wx ZSHC                        |
| .metar 机场ICAO代码         | 请求机场 ID 的天气（METAR）。                                | .meter ZSHC                     |
| .wallop 消息内容            | 向网络上的所有 Supervisors 发送指定消息。（注：.wallop 指令不仅限用于“投诉”，同样可用于向 Supervisors 寻求“帮助”） | .wallop we need help            |
| .copy                       | 将当前选项卡中所有聊天记录复制到剪贴板 |                                 |
| .clear                      | 清除当前选项卡中所有聊天内容  |                                 |
| .reloadrules                | 重新加载模型匹配规则。                                       |                                 |
| .sq 应答机代码              | 将您的应答机设置为指定的代码。 也可以使用 .xpdr、.xpndr、.x 或 .squawk。 | .sq  2000                       |
| .com1 频率                  | 将 `COM1` 无线电设置为指定频率。                             | .com1 133.075                   |
| .com2 频率                  | 将 `COM2` 无线电设置为指定频率。                             | .com2 133.075                   |
| .com 1                      | 启用 `COM1` 无线电进行传输。                                 |                                 |
| .com 2                      | 启用 `COM2` 无线电进行传输。.                                |                                 |
| .com both                   | 同时开启两个 `COM` 无线电接收。                              |                                 |
| .towerview [IP 地址] [呼号] | 以Observer模式将 vPilot 连接到代理服务器（例如 Euroscope 提供的），以创建机场塔台视角。 IP 地址默认为 127.0.0.1 (localhost)，呼号默认为 TOWER。 |                                 |
| .aircraft                   | 开启一个新窗口以显示该区域内每架飞机的详细信息。             |                                 |
| .debug                      | 显示调试窗口。                                               |                                 |
| .ignore 呼号                | 将指定呼号的飞机添加到忽略列表中。 否则，vPilot 会渲染列表中的任何飞机的飞机模型。 |                                 |
| .unignore 呼号              | 从忽略列表中删除指定呼号的飞机。                             |                                 |

## 断开与 VATSIM 的连接

当您准备好与 VATSIM 断开连接时，只需按下 vPilot 主窗口上的 `Disconnect` 。 此时管制员列表将被清空，并且 vPilot 添加到 模拟器 的所有飞机都将被删除。 您也将会断开与语音服务器的连接。

请注意，如果您关闭 模拟器，vPilot 将自动断开网络连接。 如果您切换机场或在 SIM 中加载不同的机模，您也将暂时断开连接。同时，当您需要更换您的呼号时，也需要首先断开与VATSIM连飞服务器的连接，并在重新连接时输入您想使用的呼号。

## 下载更新

每次启动 vPilot 时，它都会向 vPilot 服务器发送请求，以查看是否有可用的更新版本。 如果有，会提示您一条类似于图所示的消息。

如果您选择下载可用更新，vPilot 将下载更新的安装程序，并显示进度条。 下载完成后，vPilot 将退出并运行安装程序。 安装更新后，您可以选择再次启动 vPilot。

***注意：由于 Velocity 的实施，请确保您的 vPilot 版本已更新至 v3.x版本 ，否则将无法接入 VATSIM***

## 远程运行vPilot（就无脑复制黏贴Google翻译 懂得看下）

如果您想在运行模拟器的机器以外的机器上运行主 vPilot 用户界面，您可以通过拆分网络配置运行 vPilot 来实现。在此配置中，您实际上将运行两个 vPilot 副本。第一个副本在与模拟器相同的机器上以“主机”模式运行。第二个副本在另一台计算机上以“远程”模式运行。远程副本通过网络与主机副本通信。

要在主机或远程模式下启动 vPilot，您可以使用安装 vPilot 时在开始菜单程序列表中创建的特殊快捷方式。同样，在 sim 计算机上，以“主机”模式启动 vPilot。在您想要查看 vPilot 用户界面的另一台计算机上，以“远程”模式启动 vPilot。第一次以远程模式启动 vPilot 时，它会提示您进入“设置”窗口并输入主机的 IP 地址。您还可以配置 vPilot 将使用哪个端口连接到主机。在主机副本和远程副本中，端口设置必须配置为相同的值。此端口也必须在主机的防火墙中打开。

请注意，两个副本必须运行完全相同版本的 vPilot，以便它们相互连接。

您会注意到在主机模式下启动 vPilot 有两个快捷方式，在远程模式下启动它有两个快捷方式。一种快捷方式包括语音通信，另一种则没有。这允许您选择哪台机器将处理与 VATSIM 语音服务器的连接以与 ATC 通信。您必须选择主机或遥控器来处理语音通信。您不能同时在主机和遥控器上运行语音通信。

## 共享驾驶舱（Observer）模式

vPilot 支持以 Observer 连接，这样您的飞机就不会出现在网络上的其他用户面前。 此功能旨在用于共享驾驶舱操作。 要使用此功能，第一个飞行员应该正常连接到网络，第二个飞行员应该以 Observer 模式连接。 第二个飞行员必须使用与第一个飞行员相同的呼号，并在末尾附加一个字母。

例如，如果第一个飞行员的呼号是CCA081，那么第二个飞行员应该使用 CCA081A。 （任何字母都可以，不一定是 A。）通过这样做，第二个飞行员的 vPilot 副本将不会在 模拟器 中显示第一个飞行员的飞机。

## 常见问题

掉线

afv掉线

![QQ图片20220425141139](https://user-images.githubusercontent.com/104274235/165033691-e1cc4360-7cf1-4b33-a983-9a2d1fa19579.png)


## 获取帮助

如果在阅读文档后，您仍有关于安装、配置或使用 vPilot 的问题，请在转到  [vPilot 官方文档](https://vpilot.rosscarlson.dev/Documentation#networking) 或在 [VATSIM vPilot Forum](https://forums.vatsim.net/forum/329-vpilot/) 中发布您的问题。
