# 前言

本文旨在介绍使用Microsoft Flight Simulator（又称Microsoft Flight Simulator 2020或MSFS2020，以下简称MSFS）进行连线飞行，以及在此过程中可能涉及到的有关MSFS或其他相关软件的使用方法，并非MSFS或其他所提到的相关软件的使用教程。

由于MSFS以及其他相关软件还在不断更新和升级，我们将会不断地进行更新，以保证本文档的准确性和时效性。

# 准备工作

使用MSFS进行连飞之前，您首先需要确保您已经安装或更新了MSFS的最新版。本文将主要介绍通过vPilot将MSFS连接到VATSIM连飞网络，如果您希望使用其他连飞软件，请自行参阅相关软件的使用文档。

## vPilot

### vPilot的下载、安装及基本设置
有关vPilot下载、安装以及通用的基本设置方法，请参阅vPilot使用手册（链接）进行设置，本文将不再对其进行说明。

### vPilot模型匹配（MSFS）
不同于P3D或FSX，vPilot对于MSFS的模型匹配机制有着明显的不同。

在 `Settings` 中我们可以看到，对于MSFS的模型匹配，vPilot并不会对您模拟器所安装的AI机模/涂装进行扫描。也就是说，如果您希望在MSFS上使用vPilot的模型匹配功能，您需要通过客制化模型匹配规则来实现。

![QQ图片20220426160408](https://user-images.githubusercontent.com/104274235/165252486-8bd19982-f8f7-46f8-8ca0-1a72bb619e46.png)


根据客制化模型匹配规则的介绍，您可以根据您的需求自行创建一个规则文件，也可以从网络上下载规则文件。除此之外，您也可以使用第三方的软件（如：[Model Matching Magic](https://flightsim.to/file/15266/model-matching-magic)(flightsim.to)）对您已经安装到MSFS的机模/涂装进行扫描，并根据您的选择生成一个相应的模型匹配规则。

有关AIG机模的安装请参阅P3D to VATSIM.

下面我们将对本软件进行一个简单的介绍。

### 使用Model Matching Magic创建规则文件

启动软件后，将自动识别您的Community文件夹路径。如果
