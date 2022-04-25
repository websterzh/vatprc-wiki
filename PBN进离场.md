# PBN进离场
众所周知，VATPRC空域大部分机场已经主用PBN/RNAV进离场程序，本节主要内容为描述如何正确的选择和使用PBN进离场程序。

## 选择正确的离场程序
以北京首都北向为例。

我们使用VATPRC飞行员中心内的航图（eAIP），选择带有“RNAV”字样的SID航图页，可以发现该航图页上包含了三条跑道的离场程序。

一般而言，每个离场程序都绑定了某一条跑道，因此只需要根据计划用于离场的跑道选择相应的离场程序即可。例如计划使用01号跑道离场，离场点为`MUGLO`，由图中可知，使用的离场程序为`MUGLO-9YD`（在机模上因为编码的原因可能会被缩写为`MUG9YD`）。

![image](https://user-images.githubusercontent.com/40542435/164958848-279f39a4-dec9-4641-9ec9-0fc8e0999951.png)


## 选择正确的进场程序及过渡点
仍然以北京首都北向为例。

我们继续使用VATPRC飞行员中心内的航图（eAIP），选择带有“RNAV”字样的STAR航图页，可以发现该航图页上所有进场程序均同时适用于三条跑道。

一般而言，在多跑道机场，每个进场程序并不一定绑定特定的一条跑道，且一般而言同一运行方向的平行跑道从同一进场走廊口进来有可能使用同一进场程序。例如从`DUMAP`进港，计划使用01号跑道进场，由图中可知，使用的进场程序为`DUMAP-9ZA`（可能由于编码的原因被缩写为`DUM9ZA`）。

![image](https://user-images.githubusercontent.com/40542435/164958860-e9de1c90-eac9-45bb-bf4b-112a06d8bad6.png)


由图中`DUMAP-9ZA`进场程序可知，起始进近点（IAF）为`AA421`。进一步找到01号的RNAV盲降仪表进近图，如图所示，`DUMAP-9ZA`可以接到`RNAV ILS/DME z 01`号进近上。因此，此时需要选择的过渡点（Trans/Transition）即为`AA421`。当你选择进近方式时，你的FMC/FMGC会提示你选择过渡点。

![image](https://user-images.githubusercontent.com/40542435/164969046-77209dd4-b5c6-4a17-b62a-019895928d6b.png)


以下为一些不同机型的举例。

![548CDDF8EECCE026532AEFD3949A1925](https://user-images.githubusercontent.com/40542435/164958898-b32185f4-efac-41db-9741-f5dfe669a86e.png)
（PMDG）

![67379FF06BCC6CF37C4C17EED8171C30](https://user-images.githubusercontent.com/40542435/164958903-d37fbfb0-815a-4086-8993-d7ff39cf5b6f.png)
（QW787）

![1539F3CC4F24BF08A0446FF2DD3B96CB](https://user-images.githubusercontent.com/40542435/164958908-aef92a7b-75d9-4f2d-aa46-b4efd68a03f0.png)
（MSFS2020）
