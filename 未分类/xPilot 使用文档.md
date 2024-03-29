# xPilot 使用文档

xPilot是一个X-Plane机组客户端，可以让您连接到VATSIM网络，以便您可以在网络上飞行，并实时接收虚拟空中交通管制服务。

+ 本文档翻译自 [xPilot官方文档](https://beta.xpilot-project.org/#/?id=what-is-xpilot)

+ 本文内容仅供参考，随着时间推移可能会有部分内容落后于官方文档，请以最新的官方文档为准。

+ [xPilot官网](https://beta.xpilot-project.org/)

+ [xPilot Github](https://github.com/xpilot-project/xpilot)

+ [xPilot Discord](https://vats.im/xpilot-discord)

+ [X-Plane 11 官方手册](https://www.x-plane.com/manuals/desktop/index.html)

## 系统要求

+ Windows 10或更高版本 64位

+ macOS 10.14或更高版本 64位

+ Linux 64位

+ X-Plane 11.50 或更高版本

+ CSL模型。推荐[Bluebell OBJ8 CSL](https://forums.x-plane.org/index.php?/files/file/37041-bluebell-obj8-csl-packages/)。

如果对X-Plane硬件要求有疑问，请查看X-Plane官方的[X-Plane 11系统要求](http://www.x-plane.com/kb/x-plane-11-system-requirements/)。

## 安装X-Pilot

**在安装或升级之前必须关闭X-Plane和xPilot**

以Windows 11为例 （MacOS和Linux的安装过程基本相同）

[下载xPilot](https://github.com/xpilot-project/xpilot/releases)





xPilot客户端安装目录

选择一个文件夹以安装xPilot客户端.

![InstallDirectory](https://user-images.githubusercontent.com/80950615/165933919-c4100e7e-e43b-4b88-bdcf-b22e6e57bda4.png)






X-Plane 11 目录

选择安装X-Plane 11的文件夹路径以安装xPilot插件。

![XplanePath](https://user-images.githubusercontent.com/80950615/165933938-4c6940d4-3ada-4ca7-9629-9c483033a14e.png)




现在启动X-Plane并开始飞行。 如果您正确安装了xPilot插件，您将在X-Plane插件菜单下看到一个新的xPilot子菜单。

![PluginMenu](https://user-images.githubusercontent.com/80950615/165933970-0beb38b5-8167-492f-ac6a-a660ba13a6fa.png)





### 安装CSL

xPilot 需要您必须至少安装一个CSL模型包，CSL模型本质上是X-Plane呈现在模拟器中其他飞机的飞机模型。 如果没有安装这些模型，xPilot将无法在模拟器渲染其他VATSIM用户。

首次启动xPilot时，xPilot将提示您安装CSL模型。 建议您单击 `Yes` 以自动安装和配置Bluebell CSL模型。 如果您选择否，则需要手动安装模型。

![DownloadModels](https://user-images.githubusercontent.com/80950615/165934016-370f8061-fec2-4f95-ad79-46dce383d53e.png)


下载约为560 MB，进度栏将显示下载进度。

在下载开始之前，您必须使用VATSIM网络对自己进行身份验证。 单击 `Get Token` 按钮以生成一次性下载令牌。 您的浏览器将跳转至网页。

![ModelDownloadGetToken](https://user-images.githubusercontent.com/80950615/165934032-53cef7ed-5d4c-4d4f-a0e3-9ce691c84434.png)




在xPilot客户端中输入token以开始下载。

![ConfirmDownloadToken](https://user-images.githubusercontent.com/80950615/165934046-6dd6978f-5893-45ad-a800-f915324ecd89.png)


![ModelsDownloading](https://user-images.githubusercontent.com/80950615/165934059-30857792-97ca-48f9-8978-024e70352fcb.png)






下载完成后，将提示您选择安装X-Plane 11的路径。

![ModelsXplaneFolder](https://user-images.githubusercontent.com/80950615/165934089-727776cc-a344-442d-a147-ca698a7ebd7d.png)


选择X-Plane路径并单击 `OK` 后，模型开始安装。 这会需要几分钟。 过程完成后，模型安装窗口会自动关闭，并在主窗口中显示一条消息，告诉您CSL飞机模型软件包已成功安装。 **您需要重新启动xPilot和X-plane**。

![ModelsInstalling](https://user-images.githubusercontent.com/80950615/165934113-19ec0b7a-0d32-4510-b6c3-56c6582121e1.png)



### 安装其他CSL

您可以下载并安装更多CSL包。 要启用CSL包，您将需要指定路径到X-Plane（Plugins > xPilot > Settings）中xPilot设置中安装模型的位置。 添加新文件夹路径后，您必须重新启动X-Plane。

![XplaneCSLConfiguration](https://user-images.githubusercontent.com/80950615/165934126-07d93906-040f-4a31-8a68-74b6e391e323.png)



### 启动xPilot

请您务必~~务必务必~~使用管理员身份运行xPilot

![xPilot_Adm](https://user-images.githubusercontent.com/80950615/165934142-6cf326c7-4888-4b0e-8612-22c6a3c5ea09.png)




## xPilot客户端

打开xPilot客户端后 您会看到这样的界面

![xPilot_main](https://user-images.githubusercontent.com/80950615/165934160-d6c06857-9f6f-497c-82ea-3da55f77ddfa.png)




### 登录设置

要配置xPilot客户端，请单击 `SETTINGS` 。 您将看到如下界面。

![xPilot_Settings](https://user-images.githubusercontent.com/80950615/165934179-9c394b78-651c-481c-9027-6aba254e4ea9.png)


在连接到Vatsim之前，您必须配置xPilot。

|                                                    |                          |
| -------------------------------------------------- | :----------------------- |
| VATSIM ID                                          | 填写您的VATSIM ID        |
| VATSIM Password                                    | 填写您的VATSIM密码       |
| Your Name                                          | 填写您的VATSIM注册名     |
| Home Airport                                       | 填写您的主基地（选填）   |
| VATSIM Server                                      | 选择合适的VATSIM服务器   |
| Keep xPilot window visible                         | xPilot客户端窗口始终置顶 |
| Automatically set transponder to Mode C on takeoff | 起飞后应答机自动Mode C   |

右侧的第2-7个选项供您选择哪些事件会导致提示音通知。

如果xPilot不是当前活动窗口，任务栏中的xPilot图标也会闪烁以引起您的注意。



### 音频设备

|                   |                                |
| ----------------- | :----------------------------- |
| Audio API         | 显示可用于xPilot的音频驱动程序 |
| Microphone Device | 选择您的麦克风设备             |
| Listen Device     | 选择您的声音输出设备           |
| Mic Volume        | 输入音量设置                   |
| COM1&COM2         | 输出音量设置                   |

您可以通过Microphone Device下的颜色条来调整您的麦克风音量。请确保您的音量在**绿色**范围内。蓝色表示音量太小，红色表示音量太大。



### 无线电效果

如果启用**Enable HF Squelch**，那么在HF频率时将不会听到HF频率特有的静态白噪声。 如果您想要一个真实的HF频率体验，请关闭此选项。

如果启用**Disable Radio Effects**，那么在频率里不会模拟无线电效果。如果您想要真实的无线电体验，请关闭此选项。



### 连接到VATSIM网络

要连接到Vatsim，请单击xPlot上方的 `CONNECT` 按钮。 您将看到连接窗口。 在该窗口内您需要填写呼号和执飞航空器的ICAO代码。 SELCAL代码为选填项。

![xPilot_before_connect](https://user-images.githubusercontent.com/80950615/165934194-4f663882-7c6b-4269-8ae6-740bdc910b2d.png)


Type Code是您正在飞行的航空器的ICAO代码，通常为3至4个字符。 这将使其他正在进行连飞的Vatsim用户可以在其模拟器中正常的将您以特定的航空器型号显示出来。 xPilot会根据您在Type Code中键入的内容提供可能需要的ICAO代码。 您可以通过ICAO代码，飞机模型或制造商进行搜索，xPilot将为您提供备选的结果列表。

如果填写了无效的飞机ICAO代码，xPilot将发出警告消息，提示需要您再次确认您的填写是否正确。 您可以继续使用未知ICAO代码连接。但是，其他用户可能无法在模拟器中看到您的飞机。

当准备好连接到网络时，请点按连接按钮。 如果连接成功，您将在主留言区域中看到一条消息，连接按钮将变为浅蓝色，提示文字将变更为`Disconnect`。 您当前位置范围内的管制（如果有）将出现在客户端左侧的**Nearby ATC**列表中。

成功连接后，您的呼号将显示在`Settings`按钮的右侧。



请注意，有关使用共享驾驶舱（Observer）模式的详细信息，请参阅共享驾驶舱模式。

![xPilot_main_connected](https://user-images.githubusercontent.com/80950615/165934214-148c54cb-4143-4f19-8d03-aa36b31a697d.png)


### 由于低帧速率而断开连接

VATSIM要求X-Plane用户在飞行期间保持每秒至少20帧的速度。这样做的原因是为了防止一种被称为"time dilation"的现象，即X-Plane的模拟速度低于实时速度，这会导致飞机在雷达上的飞行速度低于其地面速度报告的速度。X-Plane执行严格的最低20 FPS标准，以确保模拟速率实时运行。如果模拟器帧数长时间低于20帧，则可能导致Xpilot自动从连飞服务器断开。你可以在[这里](https://www.x-plane.com/kb/the-simulators-measurement-of-time-is-slow/)阅读更多信息



### 设置应答机

在 VATSIM 上进行连线飞行时，您需要将应答机在 Standby Mode（MODE S）和 Mode C 之间切换。Mode C 需要在您进入开放跑道和空中时使用，开启 Mode C 后，管制员将能够在其范围内查看您的高度。如果由于机场运行要求，飞行器在地面移动时需要将应答机Mode C ，将会在对应管制员的ATC info或通波中标注。参见管制空域内的飞行——ATC info。

- 当您在模拟器中飞机的应答机面板切换应答机模式时，xPilot 将同步检测应答器模式的变化。也就是说，当模拟器中飞机的应答机处于 Mode C 时，您会看到 xPilot 主窗口上的 `mode C` 按钮绿色亮起，表明此时Xpilot检测到了模拟器内飞机应答机状态的变化。


![xPilot_ModeC](https://user-images.githubusercontent.com/80950615/165934239-7cf4bc3c-9941-4f26-85cb-bc56d9de1a4a.png)

  

- 如果Xpilot没有同步应答机模式，那么您需要手动在 xPilot 管理应答器模式，只需单击 xPilot 主窗口上的 `mode C` 按钮即可。 `mode C` 按钮绿色表示应答机已经处于 Mode C  再点~~亿~~ 一次则会回到Standby Mode。

这两个选项也适用于 squawk ident（应答机识别）。当您第一次联系某个频率时，管制员可能会要求您应答机识别 。这会使得您在他的管制范围内以不同的方式显示，从而帮助他在他的空域中找到您。如果您被要求应答机识别，您可以按飞机应答机面板上的 ident 按钮，或者点击 xPilot 主窗口上的 `IDENT` 按钮 。当 xPilot 将 ident 信号发送到网络时，xPilot 主窗口上的 `IDENT` 按钮将高亮为绿色。


![xPilot_ModeC_IDENT](https://user-images.githubusercontent.com/80950615/165934255-47060797-d4c4-4057-bad1-292543b8e4c7.png)


### 与空中交通管制通信

当您连接到Vatsim时，范围内的所有管制员都将显示在xPilot客户端窗口左侧的管制员列表中，列表按管制设施类型分组。列表中的每个条目都将写有管制员的呼号和频率。如果您将鼠标悬停在呼号上，则会弹出一个标签，显示该管制员的注册名。

为了与管制员进行通信，只需在飞机无线电面板中调整无线电的频率即可。机载无线电还必须启用发射和接收模式。在xPilot客户端窗口左上方的无线电面板，当该无线电频率启用传输和接收模式时，TX/RX标签将高亮为白色。

在下面的示例中，COM1频率为122.800 启用COM1进行发送和接收，如白色TX/RX指示器所示。 COM2传输和接收则被关闭。

**请注意，所有管制员指令应当在`Messages`窗口回复,请勿在私聊窗口回复。**


![COM1](https://user-images.githubusercontent.com/80950615/165934270-f816057f-bd77-4dd9-9447-a2ec32f73013.png)



### SELCAL

如果您在接入 VATSIM 时输入了 SELCAL 代码，那么管制员可以使用该代码向您的飞机发送 SELCAL 提示音。 SELCAL主要使用在嘈杂的 HF 频率。 机组通常会调低音量，这样他就不会受到 HF 噪音的干扰，当管制员需要通过 HF 与他交流时，管制员会发送 SELCAL 提示音以引起他的注意。 VATSIM 不开设 HF 频率，但出于现实目的，会通过VHF模拟HF频率且海洋管制员仍将模拟 SELCAL 过程

如果您收到管制员发送的 SELCAL 消息，xPilot 将发出提示音并在主消息区域显示一条消息。



### 请求ATIS

要请求ATIS，请双击管制员列表中的ATIS标签。ATIS信息将会出现在主信息区。
您还可以使用请求ATIS信息`.atis <Callsign>`的点命令。有关详细信息，请参阅点命令一节。



### 提交飞行计划

您必须使用My Vatsim上的飞行计划服务网站提交飞行计划。 如果您单击客户端中的`Flight Plan`按钮，则会跳转到My Vatsim网站。

您将会看到如下界面

![Flightplan](https://user-images.githubusercontent.com/80950615/165934293-d1ec602a-15f6-493b-b679-503e8ff24371.png)



以下为[Flight Plan](https://my.vatsim.net/pilots/flightplan) 界面的中文释义：

| 界面原文             | 中文释义                                                     |
| -------------------- | ------------------------------------------------------------ |
| Callsign             | 呼号                                                         |
| Flight Rules         | 飞行规则                                                     |
| Aircraft Type (ICAO) | 航空器机型(ICAO)                                             |
| Wake Category        | 航空器尾流等级                                               |
| Equipment (ICAO/FAA) | 无线电通信、导航及进近助航设备与能力                         |
| Transponder          | 监视设备与能力                                               |
| Departure            | 出发机场                                                     |
| Off Block UTC        | 预计撤轮挡UTC时间                                            |
| Altitude             | 巡航高度                                                     |
| Airspeed             | 巡航速度                                                     |
| Destination          | 目的地机场                                                   |
| Alternate            | 目的地备降机场                                               |
| Enroute Time         | 航路飞行时间                                                 |
| Fuel Endurance       | 燃油可用时间                                                 |
| Route Details        | 航路                                                         |
| Other Details        | 其他情报 详见[新版飞行计划规范及指南](https://forum.vatprc.net/topic/2888-vatsim%E6%96%B0%E7%89%88%E9%A3%9E%E8%A1%8C%E8%AE%A1%E5%88%92%E8%A7%84%E8%8C%83%E5%8F%8A%E6%8C%87%E5%8D%97/) |
| Voice Rules          | 通讯方式                                                     |

以下为三种 `Voice Rules` 方式的释义：

| 通讯方式     | 代码 | 描述                                     |
| ------------ | ---- | ---------------------------------------- |
| Voice        | /v/  | 可以接受语音管制并通过语音回复           |
| Receive Only | /r/  | 可以接受语音管制服务，但只能通过文字回复 |
| Text Only    | /t/  | 只能接受文字管制                         |



### 私聊信息

有时，您会希望通过私聊信息与其他机组或管制员联系。或者他们会通过私聊信息与您联系。当收到一条新的私聊信息时，一个新的选项卡就会出现，以黄色突出显示，同时伴随有“嘀嘀嘀”的提示音。单击选项卡时，将显示该聊天的消息区域，并且标签文本将变白。消息区域的第一行将显示发起私聊用户的注册名。如果在选项卡被选中时收到新消息，则标签将再次变成黄色。

要回复私聊信息，请在聊天选项卡底部的命令行中输入您的消息，然后按Enter。您发送的消息将以青色颜色出现在消息区域中。您收到的消息将以白色出现。

您可以通过在管制员列表中的管制员上右键单击，然后从菜单中选择`Open Private Chat`来向管制员发送私聊信息。这将创建一个新选项卡。您可以输入消息，然后按Enter发送它。

您还可以使用 .chat 命令来启动私聊信息会话。有关详细信息，请参阅点命令的部分。



### 点命令

xPilot支持以下点命令，可以在任何选项卡中的消息历史记录下方输入命令行中。

| 命令                                 | 描述                                                         |
| ------------------------------------ | ------------------------------------------------------------ |
| `.chat <Callsign> `                  | 打开一个新的私聊信息聊天选项卡。 您可以指定要发送的初始消息字符串。你也可以使用 `.msg` |
| `.clear`                             | 清除当前选项卡的内容                                         |
| `.atis <Callsign>`                   | 请求指定管制席位的信息或者ATIS。                             |
| `.wx <Airport ICAO>`                 | 请求指定机场的METAR。您也可以使用 `.metar`                   |
| `.wallop <Message>`                  | 向与网络连接的所有Vatsim SUP发送“ wallop”。                  |
| `.x <Squawk-Code>`                   | 将您的应答器设置为指定的应答机代码。 你也可以使用 `.xpdr`, `.xpndr`  `.squawk` |
| `.com1 <Frequency>`                  | 将COM1无线电设置为指定的频率。                               |
| `.com2 <Frequency>`                  | 将COM2无线电设置为指定的频率。.                              |
| `.rx com# On/Off`                    | 切换在指定的COM无线电上接收。 例如：`.rx com1 on`            |
| `.tx com#`                           | 启用COM1或COM2无线电进行传输。 例如： `.tx com2`             |
| `.towerview <IP-Address> <Callsign>` | 以Observer模式将 xPilot 连接到代理服务器（例如 Euroscope 提供的），以创建机场塔台视角。 IP 地址默认为 127.0.0.1 (localhost)，呼号默认为 TOWER。 |
| `.ignore <Callsgin>`                 | 将指定呼号的飞机添加到忽略列表中。 否则，xPilot 会渲染列表中的任何飞机的飞机模型。 |
| `.unignore <Callsign>`               | 从忽略列表中删除指定呼号的飞机。                             |
| `.ignorelist`                        | 显示忽略列表                                                 |
| `.simip`                             | 设置运行X-Plane的计算机的IP地址。详见**远程运行 xPilot**     |
| `.visualip`                          | 详见**远程运行 xPilot**                                      |



### 断开与VATSIM网络的连接

当您准备断开与Vatsim的连接时，单击xPilot客户端上的`DISCONNECT`按钮。 

如果关闭模拟器，xPilot将自动断开从网络的连接。 如果在模拟器中切换机场或加载不同的飞机，您也将被断开连接。



### 远程运行xPilot

如果你有一台或多台运行X-Plane视觉系统的计算机的网络设置，你可以配置xPilot将飞机注入每台机器。必须首先在每台机器上运行xPilot安装程序，以便安装xPilot插件。
在xPilot中，使用命令`.visualip <VisualMachine1> <VisualMachine2>...` 设置机器的IP地址。例如`.visualip 192.168.1.50 192.168.1.60`。设置IP地址后，必须重新启动xPilot，更改才能生效。带有的机器IP地址将保存在xPilot客户端配置中，以便下次启动xPilot时使用。要清除可视机器IP，请使用命令。visualip（不含IP地址）。
或者，您可以在运行X-Plane的机器之外的另外一台计算机上运行xPilot客户端。使用命令`.simip `设置运行X-Plane实例的计算机的IP地址。例如：`.simip 192.168.1.100`。如果要清除IP地址，请输入命令` .simip`。在更改配置文件之前，必须关闭xPilot客户端。



### 共享驾驶舱（或观察者）模式

xPilot支持在obs模式下连接，因此您的飞机不会出现在Vatsim网络上的其他用户。 此功能一般在共享驾驶舱时使用。 要使用此功能，第一个飞行员应正常连接到网络，第二个飞行员应在obs模式下连接。 第二名飞行员必须使用与第一个飞行员相同的呼号，并将信件附加到最后。

例如，第一个飞行员的呼号是CES2159，则第二个飞行员应使用CES2159A、CES2159B等等。 任何字母后缀都可以工作。



### 更新xPilot

每次启动xPilot时，它都会检查是否有新版本可用。如果有新版本可用，系统将提示您下载并安装。

![NewVersionAvailable](https://user-images.githubusercontent.com/80950615/165934330-0a725b47-cba8-4b41-b1f1-78d85940f895.png)



***注意：由于 [Velocity](https://www.vatprc.net/announcement/3642) 的实施，请确保您的 xPilot 版本已更新至 xPilot v2.0.0-beta.1或更高版本 ，否则将无法连接到 VATSIM网络***



如果单击`No`，下次打开xPilot时将再次出现提示。
单击`Yes`将开始下载过程。下载完成后，xPilot将关闭，安装程序将打开。
**安装更新之前必须关闭X-Plane，否则无法正确更新xPilot插件。</u>**

![NewVersionDownloading](https://user-images.githubusercontent.com/80950615/165934356-c6602e2e-921e-4245-b045-d1bfed61f65b.png)



## X-Plane内的xPilot

### 设置

可以通过X-Plane内菜单Plugins > xPilot > Settings进行设置。

所有xPilot插件设置都将保存到X-Plane 11/Resources/plugins/xPilot/Resources文件夹中名为Config.json的文件中。


|                    |                                                              |
| ------------------ | ------------------------------------------------------------ |
| 自动显示通知面板   | 如果启用了此选项，则如果收到了新的无线电文本消息，它将显示在X-Plane窗口右上方的小半透明面板中。 |
| 隐藏通知面板       | 此选项设置了通知面板会在几秒钟后自动消失。                   |
| 通知面板位置       | 此选项允许您在X-Plane窗口中设置通知面板的位置。              |
| 显示呼号标签       | 如果启用了此选项，则将呼号标签放在模拟器中的所有飞机上方。   |
| 呼号标签颜色       | 您可以设置自定义的飞机呼号标签颜色。有四种预定义的颜色：黄色，红色，绿色和青色。您可以通过单击左侧的颜色正方形来选择自己的颜色。 |
| 最大呼号标签距离   | 此选项设置了您可以看到飞机标签的距离。                       |
| 默认飞机类型ICAO   | 如果没有合适的CSL模型，则使用的后备飞机ICAO类型指定器可用于飞机。 |
| 启用发送指示灯     | 启用此选项，当您按下推销时，在X-Plane窗口左上角的绿色发送指示灯。 |
| 启用飞机发动机声音 | 启用此选项，将环境发动机声音添加到其他飞机上。               |
| 飞机发动机音量     | 该滑块更改其他飞机的发动机音量                               |



### 设置Push To Talk

#### 绑定操纵杆按钮

要将PTT分配给操纵杆按钮，请在列表中查找您要设置的按键并单击编辑

![X-Plane_Settings_Joystick](https://user-images.githubusercontent.com/80950615/165934377-b491bb37-8975-4f7d-9e0d-3bd731dca85d.png)


X-Plane Settings Joystick.png

在搜索栏中搜索xPilot并选择 **xPilot: Radio Push-to-Talk (PTT)**

![X-Plane_Settings_JoystickPTT](https://user-images.githubusercontent.com/80950615/165934392-d2e9f36e-483f-42a3-b767-033dbccc6d0f.png)



然后单击`Apply`

操纵杆PTT绑定完成。



#### 绑定键盘按钮

在X-Plane设置中打开Keyboard菜单。 在搜索栏中搜索”xPilot“并在搜索结果中查找xPilot：Radio Push-to-Talk（PTT） 选项。单击 **+** 按钮，然后按下您想设置为PTT的键盘键。设置键盘键后，单击`Done` 以保存。

![X-Plane_Settings_KeyboardPTT](https://user-images.githubusercontent.com/80950615/165934422-ed4e503e-b006-46ed-bccf-8a91d6127c9c.png)


完成键盘PTT绑定操作。



### CSL配置

xPilot没有需要安装或配置的复杂或特殊模型匹配规则。 在使xPilot之前，您必须至少安装一个CSL包。 最受欢迎的模型是Bluebell CSL。 首次安装xPilot时，将提示您安装CSL包。

在xPilot插件设置Plugins > xPilot > Settings中，有一个部分可以将路径定义到安装CSL模型集的位置。 您最多可以定义七个不同的路径。

![XplaneCSLConfiguration](https://user-images.githubusercontent.com/80950615/165934455-0274740a-1389-4f87-897c-dfafc65154b3.png)

要定义新路径，请单击“浏览”按钮，然后浏览到文件夹，或手动输入完整路径。 如果有多个子文件夹，xPilot将搜索文件夹以寻找其他模型。

通过取消选中启用的复选框，您可以禁用从加载X-Plane时被加载的路径。

每次加载xPilot客户端时，都会验证您安装了CSL型号并正确配置。 如果找不到模型，或者该路径无效或未启用，则连接按钮将被禁用，并且在主消息区域中将显示红色错误消息

![ClientCSLError](https://user-images.githubusercontent.com/80950615/165934470-599cfa5a-4d0f-4a31-b5d0-ea1eb7d1411d.png)


如果看到此错误，请确保安装了CSL包（例如Bluebell CSL），并且该路径在xPilot插件设置中正确配置。 进行更改后，重新启动xPilot和X-Plane。

每当您更改CSL配置时，都必须重新启动X-Plane才能生效。



### 按键绑定

有几个xPilot命令可以绑定到X-Plane中的一个或多个键盘键、操纵杆按钮或开关。如果您不熟悉如何在X-Plane中设置命令快捷方式，请参阅[X-Plane 11手册](https://www.x-plane.com/manuals/desktop/index.html#configuringkeyboardshortcuts)了解更多信息。

可用的X-Plane命令：

- **Radio Push to Talk (PTT)**
  连接到网络时，通过无线电频率进行传输。

- **Toggle Default X-Plane ATIS**
  启用或禁用默认的X-Plane ATIS。当连接到网络时，xPilot将自动禁用X-Plane默认ATIS，但您可以使用此命令（或通过xPilot插件菜单）再次启用它。

- **Toggle Nearby ATC Window**
  显示或隐藏Nearby ATC窗口。

- **Toggle Aircraft Labels**
  显示或隐藏飞机标签。

- **Toggle Notification Panel**
  显示或隐藏通知面板。

- **Toggle Message Console**
  显示或隐藏短信控制台。

- **Toggle TCAS Control**
  请求或释放TCAS。

  

### 信息控制台

除了使用xPilot客户端界面发送或接收文本消息或私聊信息外，还可以使用X-Plane中的文本消息控制台。您可以通过`Plugins > xPilot > Text Message Console`台打开文本消息控制台

私聊信息将出现在文本消息控制台窗口的单独选项卡中。要关闭选项卡，请单击蓝色的“X”。要开始新的私聊信息，请键入命令`.chat <callsign>`（CALLSIGN是您要向其发送消息的用户的呼号）并按enter键。将打开一个新选项卡，标题为您指定的呼号。在选项卡底部的消息合成区域中键入消息，然后按键盘上的enter键发送消息。



### 附近的空中交通管制

附近的ATC窗口按设施类型显示在范围内的控制器；该列表包括呼号、频率和管制员姓名。有两个可用的操作按钮。第一个按钮将请求管制席位信息（管制员ATIS），第二个按钮将把COM1无线电频率调到该管制席的频率。

![nearby_atc](https://user-images.githubusercontent.com/80950615/165934494-6424fad1-28e8-4df5-8734-9837208278f0.png)



## 寻求帮助

如果您在配置xPilot时遇到问题，请加入[xPilot Discord服务器](https://vats.im/xpilot-discord)。或者，你也可以在[xPilot论坛](https://forums.vatsim.net/forum/352-xpilot)上发帖。



## X-Plane意外退出

如果X-Plane闪退，错误信息会保存于Log.txt中的最后一行。日志通常会指示导致应用程序崩溃的原因。如果xPilot导致X-Plane闪退，错误信息将会在错误日志中的最后一行写出。

 --=={This application has crashed because of the plugin: xPilot}==--

每次重新启动X-Plane时，日志都会被覆盖，因此在重新启动X-Plane之前保存日志的副本非常重要。
X-Plane通常还会在  `X-Plane 11\Output\crash_reports` 中生成X-Plane闪退报告。
保存错误报告和日志是非常重要的。当崩溃发生后，如果没有这些信息，就不可能知道X-Plane闪退的具体原因。



## xPilot常见问题

### 飞机雷达上看不到任何TCAS目标

确保没有安装任何其他可能干扰xPilot的插件（例如XSwiftBus、XSB、X-IvAP等）。



### 网络错误：The server failed to respond to the authentication challenge

这通常是由于您与所连接的网络服务器之间的连接不良造成的。尝试检查网络情况，更改连接到其他服务器，然后重试。



### 错误：Error connecting to voice server. Please check your VATSIM credentials and try again.

如果您最近创建或重新激活了您的VATSIM帐户，您需要等待几分钟，以便您的帐户与服务器同步；在某些情况下，同步时长可能长达24小时。在同步您的帐户之前，您将无法使用语音，仅可使用文本。您还必须参加并通过**P0 : Basic VATSIM会员**考试，未通过该考试的用户将无法进行连线飞行。密码区分大小写。
