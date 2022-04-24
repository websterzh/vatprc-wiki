# vPilot 使用文档

本文档翻译自 [vPilot 官方文档](https://vpilot.rosscarlson.dev/Documentation)。

本文内容仅供参考，随着时间推移可能会有部分内容落后于官方文档，请以最新的官方文档为准。

## 目录

- 系统要求
- 安装
- 启动 vPilot
- 配置
- 模型匹配
- 创建客制化模型匹配规则
- 模型匹配规则介绍
- 连接到 VATSIM
- 设置应答机
- 与管制员沟通
- SELCAL
- 请求管制员信息（获取文字ATIS）
- 提交飞行计划
- 私聊信息
- 点命令
- 断开与 VATSIM 的连接
- 下载更新
- 远程运行 vPilot
- 共享驾驶舱（观察员）模式
- 获取帮助
- vPilot 最终用户许可协议

## 系统要求

- 操作系统：Microsoft Windows 7, Windows 8.1 或 Windows 10
- 运行库：Microsoft .NET Framework 4.7.2
- 磁盘空间：在存储应用程序数据和用户文档的盘上 100 MB 的可用空间
- 下列模拟飞行软件的一个或多个：
  - Microsoft Flight Simulator X with Acceleration or Service Pack 2 (FSX)
  - Microsoft Flight Simulator X Steam Edition (FSX:SE)
  - Lockheed Martin Prepar3D (P3D)
  - Microsoft Flight Simulator (MSFS 2020)

## 安装
下载 vPilot 后，双击下载的文件开始安装。 默认情况下，vPilot 安装在C:\Users\用户名\AppData\Roaming文件夹中，以免出现文件权限问题。 如果您更改安装文件夹，请务必指定一个不需要管理员权限的文件夹，以便 vPilot 能够写入其配置文件

安装完成后，您可以选择启动 vPilot

## 启动 vPilot
- 要启动 vPilot，请双击桌面图标（如果您选择在安装过程中创建一个）或在程序列表中找到 vPilot 并从那里启动它。 vPilot 会在 模拟飞行软件 外部运行，因此它不像其他一些插件客户端那样从模拟器菜单启动
- 第一次运行 vPilot 时，您将看到一个窗口弹出，该消息表明您尚未完全配置 vPilot，单击“是(Y)”打开设置窗口并配置 vPilot
- vPilot 启动后，它会立即尝试通过 SimConnect 连接到 sim 。 如果 sim 尚未运行，它将每 10 秒尝试一次，并在最终建立连接时在主消息区域显示一条消息（以Lockheed Martin Prepar3D v5为例）

## 配置
- 要配置 vPilot，请单击Settings按钮。 您将看到如图所示的画面。
### Network
- 在本页，您只需输入您的 VATSIM CID/密码、您的注册名和您的家乡机场，并且选择您要连接的 VATSIM 服务器，您因选择在您网络环境下连接最稳定的服务器，您将能够看到连接到任何一个服务器上的其他飞行员和 sim ，它们都是相互关联的
### Notifications
- 通知选项卡上的项目允许您选择当 vPilot 不是置顶窗口时哪些行为将导致任务栏闪烁。
- Flash taskbar icon for new private message              收到新的私信时任务栏闪烁
- Flash taskbar icon for text radio message               收到新的无线电文字消息时任务栏闪烁
- Flash taskbar icon for SELCAL message                   收到新的SELCAL消息时任务栏闪烁
- Flash taskbar icon when disconnected from network       vPilot 与 VATSIM连接断开时任务栏闪烁
- Show incoming text messages in simulator                在模拟器中显示 vPilot 的文字消息（强烈建议文字机组开启本选项卡，该选项卡能够提高您的指令执行速度）
### Fonts
- 字体选项卡用于选择管制列表与文本消息的字体
### Audio
- 在这里，您可以选择您希望使用的麦克风设备，以及用作收听管制和其他飞行员的音频的设备。 如果设备尚未插入，您需要关闭“settings”窗口，插入设备，然后重新打开“settings”窗口
- 选择音频输出设备后，调整音量滑块，使音量处于自己听起来舒适的区域
- 选择麦克风设备后，调整麦克风音量滑块，同时以正常声音讲话。 使音量大部分处于绿色区域。 这将有助于确保您可以被网络上的其他飞行员和管制员清楚地听到。这一操作很重要！！！请不要伤害管制员和其他机组的耳朵！！！
- 如果您选中“Disable realistic ATC audio effects”的框，则传入的声音将不会有 VHF 无线电噪音。 通常，为了使音频真实不会选中此框。 但是，如果您很难理解 ATC 所说的内容，选中此框可能会对您有所帮助
- 如果您选中“Disable HF background noise”的框，则传入的声音将不会有 HF 无线电噪音。 通常，为了使音频真实不会选中此框。 但是，如果您很难理解 ATC 所说的内容，选中此框可能会对您有所帮助
### Push-To-Talk (PTT)
- 在此部分，您可以选择要用于 PTT 的键盘键或操纵杆/轭按钮。 只需按下标有“Set new PTT Key or Button”的按钮，然后按下要用于 PTT 的键盘键或操纵杆/轭按钮。 vPilot 将检测击键或按钮按下并相应地更新“Current PTT Assignment”
- 请注意，如果您设置键盘键用于 PTT ，并且您以管理员身份运行 FSX/P3D/MSFS，则还必须以管理员身份运行 vPilot 才能识别按键。
- 如果您不想在 VATSIM 上使用语音，请按“Clear Current PTT Assignment”按钮
### The Model Matching Tabs
- 有关模型匹配如何在 vPilot 中工作的更多信息，请参阅下面的模型匹配部分。 对于在您系统上每个受支持的模拟器，您将拥有一个选项卡
#### The Model Matching - Advanced
- 此部分允许您在模型匹配中排除模型（单独或作为整个文件夹）。 您还可以通过使用“Move Up”和“Move Down”按钮在此列表中重新排列文件夹来确定文件夹的优先级。 vPilot 将首先搜索列表中较高的文件夹用于显示您在 VATSIM 上飞行时遇到的飞机的模型
#### The Model Matching - Custom Rules
- 在这里，您可以通过从计算机硬盘加载文件来添加自定义模型匹配规则。 如果您创建了自己的文件，或者您从其他用户那里收到了文件，或者从您的 VA 网站下载了该文件，您可能会这样做。 自定义规则文件可以重新排序，以设置它们用于模型匹配的优先级。 当 vPilot 自动扫描您已安装的模型时，自定义规则始终优先于找到的模型
### Performance
- 在这里，您可以限制 vPilot 显示在您模拟器里的飞机数量。 如果您在拥挤的区域发现帧率下降，你可以降低这些数字
### Updates
- 如果勾选“Check for vPilot updates”的选框， vPilot 将会在启用时自动版本检查。 有关更新的详细信息，请参阅下载更新部分。 此选项应保持启用状态，以确保您知道何时发布新版本的 vPilot 。注：由于 Velocity 的实施，请确保您的 vPilot 版本为 v3.x ，否则将无法连线
- 此选项卡还允许您选择从“Stable”还是“Beta”更新下载。 大多数用户因选择“Stable”。 如果您想获得最新可用的 vPilot 版本，您可以将此设置更改为“Beta”，但 vPilot 的 Beta 版本尚未经过彻底测试，可能存在BUG
### Miscellaneous
- 在这里，您可以选择让 vPilot 在您的飞机离地时自动将应答机 C 模式。 如果您的飞机集成有 SquawkBox 转发器，则应不选中此复选框，因为 vPilot 将能够直接从飞机面板读取应答机模式
- 勾选“Keep window visible”可以将您的 vPilot 主窗口置顶。 请注意，如果 FSX 在全屏模式下运行，这将不起作用
