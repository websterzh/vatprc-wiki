# PBN进离场
众所周知，VATPRC空域大部分机场已经主用PBN/RNAV进离场程序，本节主要内容为描述如何正确的选择和使用PBN进离场程序，并加入相应的盲降或RNP进近。

## 选择正确的离场程序
以北京首都北向为例。

我们使用VATPRC飞行员中心内的航图（eAIP），选择带有“RNAV”字样的SID航图页，可以发现该航图页上包含了三条跑道的离场程序。

一般而言，每个离场程序都绑定了某一条跑道，因此只需要根据计划用于离场的跑道选择相应的离场程序即可。例如计划使用01号跑道离场，离场点为`MUGLO`，由图中可知，使用的离场程序为`MUGLO-9YD`（在机模上因为编码的原因可能会被缩写为`MUG9YD`）。

![image](https://user-images.githubusercontent.com/40542435/164958848-279f39a4-dec9-4641-9ec9-0fc8e0999951.png)
![image](https://user-images.githubusercontent.com/40542435/165061345-85a5c954-97b1-4b34-9d84-384b9c8ad27e.png)


## 选择正确的进场程序及过渡点
仍然以北京首都北向为例。

我们继续使用VATPRC飞行员中心内的航图（eAIP），选择带有“RNAV”字样的STAR航图页，可以发现该航图页上所有进场程序均同时适用于三条跑道。

一般而言，在多跑道机场，每个进场程序并不一定绑定特定的一条跑道，且一般而言同一运行方向的平行跑道从同一进场走廊口进来有可能使用同一进场程序。例如从`DUMAP`进港，计划使用01号跑道进场，由图中可知，使用的进场程序为`DUMAP-9ZA`（可能由于编码的原因被缩写为`DUM9ZA`）。

![image](https://user-images.githubusercontent.com/40542435/164958860-e9de1c90-eac9-45bb-bf4b-112a06d8bad6.png)
![image](https://user-images.githubusercontent.com/40542435/165064640-87b62a95-d1d4-4e10-ab28-95b521a02c1f.png)


由图中`DUMAP-9ZA`进场程序可知，起始进近点（IAF）为`AA421`。进一步找到01号的RNAV盲降仪表进近图，如图所示，`DUMAP-9ZA`可以接到`RNAV ILS/DME z 01`号进近上。因此，此时需要选择的过渡点（Trans/Transition）即为`AA421`。当你选择进近方式时，你的FMC/FMGC会提示你选择过渡点。

![image](https://user-images.githubusercontent.com/40542435/164969046-77209dd4-b5c6-4a17-b62a-019895928d6b.png)


以下为一些不同机型的举例。

![548CDDF8EECCE026532AEFD3949A1925](https://user-images.githubusercontent.com/40542435/164958898-b32185f4-efac-41db-9741-f5dfe669a86e.png)
（PMDG）

![67379FF06BCC6CF37C4C17EED8171C30](https://user-images.githubusercontent.com/40542435/164958903-d37fbfb0-815a-4086-8993-d7ff39cf5b6f.png)
（QW787）

![1539F3CC4F24BF08A0446FF2DD3B96CB](https://user-images.githubusercontent.com/40542435/164958908-aef92a7b-75d9-4f2d-aa46-b4efd68a03f0.png)
（MSFS2020）

## 盲降进近
继续上文所述的场景，我们通过了`AA421`（即IAF起始进近点）后，如果按程序建立01号跑道的`盲降`（即仪表着陆系统），只需简单按压`APP`按钮（根据机型不同称呼可能有所不同），等待`PFD/主飞行显示器`出现实心菱形并逐渐向中靠拢，可认为截获了盲降信号。

其中，`PFD`下方的菱形意为`航向道`，负责对正`盲降`的水平方向；`PFD`右侧的菱形意为`下滑道`，负责对正`盲降`的垂直方向及控制航空器的下滑速度。

一般而言，一旦建立了`航向道`，就可以向终端区管制员报告（以终端区管制员许可截获`盲降`指令时的附带报告要求为准，如建立`航向道`或建立`下滑道`），终端区管制员将会视情要求你联系塔台管制员。只需要继续跟随`盲降`系统的指引继续进近即可。
![image](https://user-images.githubusercontent.com/40542435/165066828-eff6b48a-d847-4d7e-ae8a-106d623cbfbe.png)


## RNP进近
RNP进近包括RNP(GNSS)、RNAV(GNSS)、RNP(AR)等一系列进近方式。

因eAIP公开的VATPRC空域内RNP进近有限，此处仅以A320进近大连周水子机场的`RNP-Y 10号进近`举例。

![image](https://user-images.githubusercontent.com/40542435/165061735-9f969729-92cd-483f-82c8-46373560811f.png)

如图所示，这是大连周水子机场的`IAC RNP-AR Y RWY10`航图。

当我们选择好进近程序，并跟随进近程序到达`IF`点时，高度保持在900米，并按程序调速至160节。按下`APP`按钮，预位`FINAL APP`模式
![image](https://user-images.githubusercontent.com/40542435/165061955-46edc899-45ef-4722-98a2-6e546ae2ba58.png)

当飞机通过`VIP`点（Vertical Interception Point）或`FAP`点（Final Approach Path）时，将激活`FINAL APP`模式，飞机建立稳定下滑。
![image](https://user-images.githubusercontent.com/40542435/165062200-07d1c6c9-55dd-4cbb-bdab-f8f80fe7b8c4.png)

当飞机接近决断高度时，`FINAL APP`模式将脱开，机组脱开自动驾驶，手动落地。
![image](https://user-images.githubusercontent.com/40542435/165062752-c5dc2f5b-3d25-4af3-b8db-a0b128c5b92b.png)
