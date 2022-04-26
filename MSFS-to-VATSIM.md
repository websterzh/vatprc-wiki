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

下面我们将对本软件配合AIG机模进行一个简单的介绍。有关AIG机模的安装请参阅P3D to VATSIM。

*注意：MSFS需要使用beta版的AIG软件进行安装*

### 使用Model Matching Magic创建规则文件

软件启动后，将尝试自动识别您的Community文件夹路径。如果界面上方文本框为空，则需要您点击 `...`手动选择您的Community路径。（您也可以仅选择您的AI机安装路径，这样在匹配时可以避免使用MSFS默认的机模以及其他的一些插件机）

下图的例子中，扫描的路径被设置为了AIG的安装目录。
![image](https://user-images.githubusercontent.com/25072307/165255372-1bd5839d-eb5f-4af7-86bb-ab0fd6d07537.png)

准备就绪后，点击右上角的 `Scan` ，程序将会对目标路径内的所有文件进行扫描。这个过程可能会需要几分钟的时间。

扫描完成后，程序会将所有可以使用的AI机模/涂装显示在下方的列表中：

![image](https://user-images.githubusercontent.com/25072307/165258285-77e76764-4b22-4de7-a568-8d429e8aa66b.png)

由于AIG的机模库中个别机模/涂装的机型代码、呼号代码不正确，所以在生成规则文件前，还有几个重要的步骤需要完成。

+ 检查是否所有AI机模/涂装的呼号代码和机型代码都被正确的识别了
  点击列表中的Airline ICAO或Aircraft Type标签对列表进行排序，如果出现没有内容的情况，就说明该涂装的呼号代码或机型代码没有被正确的识别。
  
  这种情况下，您可以通过勾选该涂装最右侧的复选框，将这个涂装排除(Exclude)。在生成匹配规则时，被排除的涂装将不会被写入到规则文件内。
  ![image](https://user-images.githubusercontent.com/25072307/165261337-c70cf033-0ed7-4512-8ed1-e8ee59414101.png)

  或者，您也可以双击表格中的空单元格，手动补充缺失的内容。
  
+ 设置自动替换  
  您也可以通过预设呼号代码或机型代码，批量修改那些不正确或未能正确识别的代码。
  
  + 预设呼号代码  
  
    **对于呼号代码识别错误的涂装**  
    
    如下图所示，金鹏航空的部分涂装呼号代码被识别为了“YZRC”：
    ![image](https://user-images.githubusercontent.com/25072307/165262596-7f856f00-000f-44ae-8d7d-8b45e1811604.png)
    
    根据模型匹配规则，这样会导致vPilot无法正常将这些涂装匹配至呼号前缀为“YZR”的航空器上。
    
    这种情况下，我们可以通过表格上方的 `Airline Code` 标签页，手动添加关联的呼号代码。以金鹏航空为例：
    ![image](https://user-images.githubusercontent.com/25072307/165266602-59beb403-105b-4882-b053-9a17366b0252.png)
    
    *注：所有被用户手动修改的内容都将会显示为红色，以示区分。*
    
    这样一来，生成后的匹配文件会同时将连线时呼号前缀为“YZRC”和“YZR”的航空器用涂装名中包含“Suparna Airlines Cargo”的涂装进行匹配。
    
    *注意：这样做并不会改变扫描结果，所以在列表中的呼号代码不会发生改变。*
    &nbsp;
    
    **对于呼号代码为空的涂装**  
    
    呼号代码为空的涂装，Model Matching Magic会自动将该涂装排除。如果您希望使用这些涂装，需要手动取消对它的排除，并自行在表格内添加其呼号。
    
    **注意：通航涂装通常情况下不会包含呼号代码，这种情况下仅需取消对其的排除，不需要手动添加呼号代码。**
    
  + 预设机型匹配  
  
    当Model Matching Magic无法正确识别涂装的机型代码时，该涂装的机型代码也会为空。
    
    与呼号代码不同的是，您可以通过自定义规则，在扫描时将其于正确的机型代码匹配。
    
    在Aircraft Types标签页内，您可以手动添加您希望添加的机型，以及匹配规则（正则表达式）。：
    ![image](https://user-images.githubusercontent.com/25072307/165269707-739c2ff5-4623-453c-a338-b9a09a47f997.png)
    
    假如您希望添加一个对于B737MAX 7的匹配，写入的格式如下表：
    
    | Aircraft Type | Manufacturer | Size | Engine Type | Match Rule (Regex) |
    | --- | --- | --- | --- | --- |
    | 机型代码 | 制造商 | 体型 | 发动机类型 | 匹配规则（正则表达式） |
    | B37M | Boeing | 10 | jet | `(?i)(?=.\*boeing)(?=.\*737)(?=.\*MAX 7)` |
