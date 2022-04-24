# xPilot 使用文档

xPilot是一个X-Plane飞行员客户端，可以让您连接到VATSIM网络，以便您可以在网络上飞行，并实时接收虚拟空中交通管制服务。

本文档翻译自 [xPilot官方文档](https://beta.xpilot-project.org/#/?id=what-is-xpilot)

[加入xPilot Discord](https://vats.im/xpilot-discord)

本文内容仅供参考，随着时间推移可能会有部分内容落后于官方文档，请以最新的官方文档为准。

## 系统要求

Windows 10或更高版本 64位

macOS 10.14或更高版本 64位

Linux 64位

X-Plane 11.50 或更高版本

## 安装X-Pilot

在安装或升级之前必须关闭X-Plane和xPilot

以Windows 11为例 （MacOS和Linux的安装过程基本相同）

[下载xPilot](https://github.com/xpilot-project/xpilot/releases)



xPilot客户端安装目录
选择一个文件夹以安装xPilot客户端.

![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/InstallDirectory.png)





X-Plane 11 目录
选择安装X-Plane 11的文件夹路径以安装xPilot插件。

![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/XplanePath.png)



现在启动X-Plane并开始飞行。 如果您正确安装了xPilot插件，您将在X-Plane插件菜单下看到一个新的xPilot子菜单。

![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/PluginMenu.png)



### 安装CSL

xPilot 需要您必须至少安装一个CSL模型包，CSL模型本质上是X-Plane呈现在模拟器中其他飞机的飞机模型。 如果没有安装这些模型，xPilot将无法在模拟器渲染其他VATSIM用户。

首次启动xPilot时，xPilot将提示您安装CSL模型。 建议您单击 **Yes** 以自动安装和配置Bluebell CSL模型。 如果您选择否，则需要手动安装模型。

![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/DownloadModels.png)

下载约为560 MB，进度栏将显示下载进度。

在下载开始之前，您必须使用VATSIM网络对自己进行身份验证。 单击 **Get Token** 按钮以生成一次性下载令牌。 您的浏览器将跳转至网页。

![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/ModelDownloadGetToken.png)



在xPilot客户端中输入token以开始下载。

![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/ConfirmDownloadToken.png)



![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/ModelsDownloading.png)



下载完成后，将提示您选择安装X-Plane 11的路径。

![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/ModelsXplaneFolder.png)



选择X-Plane路径并单击 **OK** 后，模型开始安装。 这会需要几分钟。 过程完成后，模型安装窗口会自动关闭，并在主窗口中显示一条消息，告诉您CSL飞机模型软件包已成功安装。 **您需要重新启动xPilot和X-plane**。

![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/ModelsInstalling.png)



### 安装其他CSL

您可以下载并安装更多CSL包。 要启用CSL包，您将需要指定路径到X-Plane（Plugins > xPilot > Settings）中xPilot设置中安装模型的位置。 添加新文件夹路径后，您必须重新启动X-Plane。

![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/XplaneCSLConfiguration.png)



## xPilot客户端

打开xPilot客户端后 您会看到这样的界面

![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/xPilot%20main.png)



### 登录设置

要配置xPilot客户端，请单击 **SETTINGS** 。 您将看到如下界面。

![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/xPilot%20Settings.png)

xPilot Settings.png

在连接到Vatsim之前，您必须配置xPilot。

VATSIM ID                    填写您的VATSIM ID

VATSIM Password      填写您的VATSIM密码

Your Name                  填写您的姓名

Home Airport              填写您的主基地（选填）

VATSIM Server            选择合适的VATSIM服务器 

如果启用**Automatically set transponder to Mode C on takeoff**，则您的飞机的应答机将在起飞后自动更改为Mode C

右侧的第2-7个选项供您选择哪些事件会导致提示音通知。

Keep xPilot window visible       xPilot客户端窗口始终置顶

如果xPilot不是当前活动窗口，任务栏中的xPilot图标也会闪烁以引起您的注意。



### 音频设备

Audio API                     显示可用于xPilot的音频驱动程序

Microphone Device   选择您的麦克风设备

Listen Device              选择您的声音输出设备

Mic Volume                 输入音量设置

COM1&COM2             输出音量设置

Microphone Device下的颜色条 请确保您的音量在**绿色**范围内 蓝色表示音量太小 红色表示音量太大





### 无线电效果

如果启用Enable HF Squelch**，则在HF频率时不会听到静态白噪声。 如果您想要一个真实的HF频率体验，请关闭此选项。

如果启用**Disable Radio Effects**，则在频率里不会模拟无线电效果。如果您想要一个真实的无线电体验，请关闭此选项。



### 连接到VATSIM网络

要连接到Vatsim，请单击xPlot上方的 **CONNECT** 按钮。 您将看到连接窗口。 需要填写呼号和飞机ICAO代码。 SELCAL代码为选填项。

Type Code是您正在飞行的飞机的3至4个字符ICAO代码。 这将使其他Vatsim用户可以在其模拟器中看到您作为正确的飞机类型。 xPilot会根据您在Type Code中键入的内容建议代码。 您可以通过ICAO代码，飞机模型或制造商进行搜索，xPilot将为您提供供您选择的结果列表。

如果填写了无效的飞机ICAO代码，xPilot将发出警告消息，提示您确认您的选择。 您可以继续使用未知ICAO代码连接。但是，其他用户可能无法在模拟器中看到您的飞机。

准备好连接到网络时按连接按钮。 如果连接成功，您将在主留言区域中看到一条消息，连接按钮将浅蓝色，按钮将更改为**Disconnect**。 您位置范围内的管制将出现在客户端左侧的**Nearby ATC**列表中。

成功连接后，您的呼号将显示在**Settings**按钮的右侧。

![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/xPilot%20main%20connected.png)

有关使用共享驾驶舱（Observer）模式的详细信息，请参阅共享驾驶舱模式。



### 与管制员通信

当您连接到Vatsim时，范围内的所有管制员都将显示在xPilot客户端窗口左侧的管制员列表中，列表按设施类型分组。列表中的每个条目都将具有控制器的呼号和频率。如果您悬停在呼号上，则会出现一个弹出标签，显示控制器的名称。

为了与控制器进行通信，只需使用COM1或COM2收音机在飞机无线电面板中调整控制器的频率即可。无线电还必须选择发射和接收。在xPilot客户端窗口左上方的无线电面板，当该COM启用传输和接收时，TX/RX标签将变白。

在下面的示例中，COM1频率为122.800 启用COM1进行发送和接收，如白色TX/RX指示器所示。 COM2传输和接收则被关闭。

![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/COM1%20TX%20RX.png)



### SELCAL

如果您在连接VATSIM时指定了SELCAL（选择性呼叫）代码，管制员将能够使用该代码向您的飞机发送SELCAL警报。在标准VHF无线电没有足够的射程，而使用嘈杂的HF频率的地区进行长途飞行时，这会引起你的注意。飞行员通常会调低音量，这样他就不必听HF静电，当需要通过HF与他通话时，管制员会发送SELCAL警报以引起他的注意。
如果收到SELCAL警报，将发出提示音，主消息区将显示一条消息提醒您。



### 提交飞行计划

您必须使用My Vatsim飞行计划服务网站提交飞行计划。 如果您单击客户端中的**Flight Plan**按钮，则默认网络浏览器将打开到My Vatsim网站

[飞行计划规范](https://forum.vatprc.net/topic/2888-vatsim%E6%96%B0%E7%89%88%E9%A3%9E%E8%A1%8C%E8%AE%A1%E5%88%92%E8%A7%84%E8%8C%83%E5%8F%8A%E6%8C%87%E5%8D%97/)



### 私聊信息

有时，您希望通过私聊信息与其他飞行员或管制员联系。或者他们通过私聊信息与您联系。当一条新的私聊信息收到时，将与发件人的呼号一起添加一个选项卡，以黄色突出显示。单击选项卡时，将显示该聊天的消息区域，并且标签文本将变白。第一行将显示用户的名称。如果在选项卡为被选中时收到新消息，则标签将再次变成黄色。

要回复私聊信息，请在聊天选项卡底部的命令行中输入您的消息，然后按Enter。您的传出消息将以青色颜色出现在消息区域中。传入消息将以白色出现。

您可以通过在管制员列表中的管制员上右键单击，然后从菜单中选择**Open Private Chat**。这将创建一个新选项卡。您可以输入消息，然后按Enter发送它。

您还可以使用.chat 命令来启动私聊信息会话。有关详细信息，请参阅点命令的部分。



### 点命令

xPilot支持以下点命令，可以在任何选项卡中的消息历史记录下方输入命令行中。

| 命令                | 描述                                                         |
| ------------------- | ------------------------------------------------------------ |
| `.chat <Callsign> ` | 打开一个新的私聊信息聊天选项卡。 您可以指定要发送的初始消息字符串。你也可以使用 `.msg` |
| `.clear`            | 清除当前选项卡的内容                                         |
| `.atis <Callsign>`  | 请求指定管制席位的信息或者ATIS。                             |
| `.wx <Station>`     | 请求指定机场的METAR。您也可以使用 `.metar`                   |
| `.wallop <Message>` | 向与网络连接的所有Vatsim SUP发送“ wallop”。                  |
| `.x <Squawk-Code>`  | 将您的应答器设置为指定的应答机代码。 你也可以使用 `.xpdr`, `.xpndr`  `.squawk` |
| `.com1 <Frequency>` | 将COM1无线电设置为指定的频率。                               |
| `.com2 <Frequency>` | 将COM2无线电设置为指定的频率。.                              |
| `.rx com# On/Off`   | 切换在指定的COM无线电上接收。 例如：`.rx com1 on`            |
| `.tx com#`          | 启用COM1或COM2无线电进行传输。 例如： `.tx com2`             |



### 断开与VATSIM网络的连接

当您准备断开与Vatsim的连接时，单击xPilot客户端上的**DISCONNECT**按钮。 

如果关闭模拟器，xPilot将自动断开从网络的连接。 如果在模拟器中切换机场或加载不同的飞机，您也将被断开连接。



### 共享驾驶舱模式

xPilot支持在obs模式下连接，因此您的飞机不会出现在Vatsim网络上的其他用户。 此功能一般在共享驾驶舱时使用。 要使用此功能，第一个飞行员应正常连接到网络，第二个飞行员应在obs模式下连接。 第二名飞行员必须使用与第一个飞行员相同的呼号，并将信件附加到最后。

例如，第一个飞行员的呼号是CES2159，则第二个飞行员应使用CES2159A。 任何字母后缀都可以工作。



## X-Plane内的xPilot

可以通过X-Plane内菜单Plugins > xPilot > Settings设置

所有xPilot插件设置都将保存到X-Plane 11/Resources/plugins/xPilot/Resources文件夹中名为Config.json的文件

![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/xpilot%20set%20in%20xp.png)

xPilot set in xp.png

自动显示通知面板
如果启用了此选项，则如果收到了新的无线电文本消息，它将显示在X-Plane窗口右上方的小半透明面板中。

隐藏通知面板
此选项设置了通知面板会在几秒钟后自动消失。

通知面板位置
此选项允许您在X-Plane窗口中设置通知面板的位置。

显示呼号标签
如果启用了此选项，则将呼号标签放在模拟器中的所有飞机上方。

呼号标签颜色
您可以设置自定义的飞机呼号标签颜色。有四种预定义的颜色：黄色，红色，绿色和青色。您可以通过单击左侧的颜色正方形来选择自己的颜色。

最大呼号标签距离
此选项设置了您可以看到飞机标签的距离。

默认飞机类型ICAO
如果没有合适的CSL模型，则使用的后备飞机ICAO类型指定器可用于飞机。

启用发送指示灯
启用此选项，当您按下推销时，在X-Plane窗口左上角的绿色发送指示灯。

启用飞机发动机声音
启用此选项，将环境发动机声音添加到其他飞机上。

飞机发动机音量
该滑块更改其他飞机的发动机音量。



### 如何设置Push To Talk

#### 绑定操纵杆按钮

要将PTT分配给操纵杆按钮，请在列表中查找您要设置的按键并单击编辑

![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/X-Plane%20Settings%20Joystick.png)

X-Plane Settings Joystick.png

在搜索栏中搜索xPilot并选择 **xPilot: Radio Push-to-Talk (PTT)**

![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/X-Plane%20Settings%20Joystick%20PTT.png)

X-Plane Settings Joystick PTT.png

然后单击**Apply** 

操纵杆PTT绑定就完成啦



#### 绑定键盘按钮

在X-Plane设置中打开Ketboard菜单。 在搜索栏中属于”xPilot“并在搜索结果中查找xPilot：Radio Push-to-Talk（PTT） 单击 **+** 按钮，然后按键盘键。设置键盘键后，单击**Done** 

![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/X-Plane%20Settings%20Keyboard%20PTT.png)

X-Plane Settings Keyboard PTT.png

这样，键盘PTT绑定就也完成了



### CSL配置

xPilot没有需要安装或配置的复杂或特殊模型匹配规则。 在使xPilot之前，您必须至少安装一个CSL包。 最受欢迎的模型是Bluebell CSL。 首次安装xPilot时，将提示您安装CSL包。

在xPilot插件设置Plugins > xPilot > Settings中，有一个部分可以将路径定义到安装CSL模型集的位置。 您最多可以定义七个不同的路径。

![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/XplaneCSLConfiguration.png)

要定义新路径，请单击“浏览”按钮，然后浏览到文件夹，或手动输入完整路径。 如果有多个子文件夹，xPilot将搜索文件夹以寻找其他模型。

通过取消选中启用的复选框，您可以禁用从加载X-Plane时被加载的路径。

每次加载xPilot客户端时，都会验证您安装了CSL型号并正确配置。 如果找不到模型，或者该路径无效或未启用，则连接按钮将被禁用，并且在主消息区域中将显示红色错误消息

![image](https://github.com/websterzh/vatprc-wiki/blob/xPilot/png/ClientCSLError.png)

如果看到此错误，请确保安装了CSL包（例如Bluebell CSL），并且该路径在xPilot插件设置中正确配置。 进行更改后，重新启动xPilot和X-Plane。

每当您更改CSL配置时，都必须重新启动X-Plane才能生效。

