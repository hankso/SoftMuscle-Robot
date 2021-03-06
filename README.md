# Control Robots with Silicon Rubber Actuators and Reinforcement Learning

## 合成与加工硅橡胶

### 硅橡胶简介
> 有机硅材料的三大主要应用：**硅油、硅橡胶、硅树脂**
> 硅油就是指各种聚硅氧烷，也就是硅橡胶的主要合成原料
> 合成硅橡胶的配方的常用成分有：
> （备注：硫化 = 固化 = 交联反应）
>- **基胶** 活性端聚有机硅氧烷，比如乙烯基封端的聚二甲基硅氧烷（PDMS），二羟基封端的PDMS（俗称107胶），聚甲基苯基硅氧烷等等。平均摩尔质量越大，黏度越大，越方便挤出而且固化后弹性强度越高
>- **增塑剂**  白炭黑（SiO2微粉，因其白颜色和类似炭黑补强效果而得名）， 碳酸钙，钛白粉，氧化锌等
>- **交联剂**  用于和原料发生交联反应的组分。交联的原理有加成型和缩合型：RTV中单组分是缩合型，利用空气中的水发生缩合交联，双组分有缩合型和加成型，对应基胶和交联剂不同。比如甲基含氢聚硅氧烷（含氢硅油），多乙烯基硅氧烷（俗称C胶，增加交联点，提高抗撕裂强度）
>- **催化剂**  又称固化剂，催化剂，加成型用含铂催化剂（常用氯铂酸），有机过氧化物（过氧化性，HTV），
>- **添加剂**  其他用于改性的添加剂，颜料，耐高低温，增粘增塑等等

### 合成选材
- 买市场上现有产品（首选）：
    - 双组分RTV硅橡胶([阿里巴巴][1688]上有不少)（首选）
    - Sylgard184（Dow Corning， USA）
    - Ecoflex00-50（Smooth-on， Germany）
    - GS-S02/GS-F01 (Godsaid, Shenzhen)
- 初步自选配方（后续根据需求可以改进）：
    - 基胶： 乙烯基封端的PDMS，100
    - 交联剂： 含氢硅油（控制性能，硅氢化反应），3-8
    - 增强剂： 白炭黑（即填料），15-30
    - 催化剂： 氯铂酸的烯烃络合物或者乙烯基硅氧烷络合物（控制交联速度，氯铂酸是高活性催化剂，络合硅氧烷会提高催化剂在反应体系中的相溶能力），0.5
    - 添加剂： 无水乙醇 - **乙醇的质量为一需要调优的参数**
- 北京顶业工贸硅橡胶（室温双组分供货）
    - 固化前
        - 高黏度（2018.03.12加工过程中，流动性差则方便3D打印成型，减慢乙醇挥发速度）
    - 固化后
        - 高拉伸强度、撕裂强度（肌肉工作于受压状态，现在看来意义不大）
        - 高伸长率
        - 高弹性模量（**2018.03.12现在看来应该为低弹性模量，即使膨胀变形很大，回复弹力也不会太大**）
        - 低硬度（比较重要，足够柔软才可以随着乙醇气化而膨胀）
        - 低压缩拉伸永久变形率（重要，不会因为长期工作于受力状态而变形）
    - 备注
        - ~~参考值：黏度15000mpas以上，拉伸强度7MPa以上，伸长率700%以上，邵氏硬度A10左右~~
        - ~~用作人造皮肤或肌肉，要皮肤色~~
        - 双组分加成型室温固化，~~可以适当升温加速固化，~~为了方便操作AB组分1:1使用
        - 需要加入乙醇制造气泡，主要有两种成型方法，模具浇灌和3D打印立体成型方法，所以要高粘度
- 预实验：
    - 主要搞明白室温固化的大致时间（2017.11.3固化时间为24h以上），升温固化的效果（虽然没做但预计乙醇挥发会更多），并且加乙醇之后分别用模具和不用模具做出来两块，然后水浴升温90°C看看效果怎么样，以此确定模具是否影响硅橡胶固化（3D打印模具，为了方便塑性，PLA材质），如果可以，是否固化后粘连在模具上（不影响不粘连，模具很好用）
- 实验方案1：
    - 取三个干燥洁净的烧杯，使用电子天平分别准确量取40gA液，40gB液，和一定量的无水乙醇（做乙醇质量梯度实验）
    - 将A液和无水乙醇混合，大力搅拌30s，不要太长时间，避免乙醇挥发过多
    - 将B液加入到混合溶液中，搅拌**均匀**
    - 将混合液倒入模具中，密封静置4h以上，或者升温到一定温度固化
    - 取出肌肉并测试其性能
- 实验方案2：
    - 用三支洁净干燥的针管抽取5mlA液、5mlB液，一定量的无水乙醇
    - 将AB液混合并加入乙醇，搅拌1min
    - 倒入模具成型，密封静置4-8h(室温15°C)或置于烘箱(干燥箱)中60°C保持约30min
- 性能测试：
    - 拉伸强度、伸长率 热学测试：高温(90°C+)下的各种性能


### 实验过程中问题记录
- 讨论硅橡胶合成方案，并提出几个需要注意的问题，详见[一些疑问][questions]
- 原料到手进行简单的混合尝试，固化了20h后仍然略微粘手，强度远远不够，判断为硅氢加成交联反应未完成，原因与温度和所加的乙醇(难道是放的时间太久混入了杂质？)有关，明天正式实验，去工训中心借用电子万能试验机
- 标准条形模具10x10x50mm | 按照实验方案2执行，暂选定乙醇用量为橡胶的体积分数20%(10mlx20%=2ml) | 柔性挤出方案2
- 尽快制作标准试样（ASTM美标），另外1031做的两枚肌肉，加了乙醇的一枚固化完成，热激活性能还未测试，没有加乙醇的未固化，原因猜测为室温较低或PLA模具影响交联反应，明天去制作三组(PLA标尺乙醇覆盖薄膜|PLA标尺乙醇不覆盖薄膜|PLA非标无乙醇|玻璃非标无乙醇)验证
- 展现方式，拍摄剪辑视频，探究的问题(图表展示)|买挤出方案2和电阻丝
- 设计制作柔性挤出头，减速步进电机皮带传动，滑块顶住针筒末端
- 制备一批肌肉测量其质量变化（含模具），从而计算出乙醇剩余量，因为膨胀效果总是不好，结果看来就是乙醇挥发的有点多，还有一个问题，高温下乙醇气化，肌肉表层的一些小囊泡会因为压力大而爆裂，乙醇就跑干净了。有个办法，肌肉固化好之后，外面包覆一层不含乙醇的普通橡胶（不能影响肌肉的膨胀），可以将乙醇保存住，如果是光固化的外层就更好了，蘸上一层用紫外光一照很快一分钟就固化了
- 之前制备的肌肉因为放置时间长而且外面没有保护层，乙醇都挥发了，失去了热膨胀特性，重新做一组，厂家提供的新橡胶比之前的质量好了一点
- 比赛快提交作品了，机械手制作基本完成，算法部分不难，就是肌肉性能是硬伤
- 讨论下一步的方案，光固化可能是突破点。发现目前已经可以做到和原论文差不多的膨胀效果了，但是答辩的时候不会展示不会说，关注一下如何展示，修改ppt，把肌肉的优点展示出来
- 1.尽快定下光固化实验方案，材料不行就再买买看。2.有种胶拿去实验室试一下，AB双组分室温20:1。3.多喷头出一个完整的方案，参考文献[Open Source Multi-Head 3D Printer for Polymer-Metal Composite Component Manufacturing](http://www.academia.edu/33578996/Open_Source_Multi-Head_3D_Printer_for_Polymer-Metal_Composite_Component_Manufacturing)作者是Joshua M. Pearce(Joshua曾经发过一篇[开源3D金属打印机](https://www.mdpi.com/2504-4494/2/1/18/htm)(普通Delta极坐标打印机的三轴向上伸出托举打印平台，用焊枪把焊条一点一点的堆焊在平台上）


### 双组分RTV硅橡胶产品常用分装形式
| 分装 | 组分A | 组分B |
| -   | - | - |
| 1   | 基胶、填料、交联剂 | 催化剂
| 2   | 基胶、填料        | 交联剂、催化剂
| 3   | 基胶、填料、交联剂 | 基胶、填料、催化剂
- 第一种可以通过调整AB比例控制固化速度，第三种可以等体积等质量混合，方便快捷。据此猜测Sylgard184为类型1，因为184需要10:1混合AB液，官方MSDS和成分表也证实；Ecoflex0050为类型3，0050等量混合即可使用，工程上操作简单
- 高、低摩尔质量的基料混合可获得想要的整体黏度，而且可以调节交联点，优化力学性能
- N、P、S会使加成型固化所用的Pt催化剂中毒，Sylgard说明书也提到不可加入含锡、氮、磷酸盐、硫化剂的物质

### 项目中碰到的问题
- [x] Miriyev教授等人论文中提到Sylgard184在乙醇存在的情况下不能固化，为什么？
    > Sylgard184是缩合型rtv双组分硅橡胶，交联反应过程中有可能会脱醇，加入乙醇会抑制交联反应。Sylgard184对外配方如下
    >- A组分： 单乙烯基封端的聚二甲基硅氧烷(PDMS)、挥发性有机化合物VOC(专利保护不公开的添加剂)、乙苯
    >- B组分： 二甲基甲基氢聚硅氧烷(含氢硅油)、四甲基四乙烯基环四硅氧烷双键封端PDMS、二甲基乙烯基化和三甲基化硅氧烷、乙苯
    > 其中基胶是双键封端的PDMS，填料未知，交联剂是含氢硅油，铂系催化剂(常用氯铂酸：H2PtCl6)

- [x] 探究乙醇的比例对肌肉热力学性能的影响
    > 并不是乙醇越多越好的，Miriyev论文中也说到经过实验发现20wt%是比较好的比例，因为膨胀效果不理想曾经有几块肌肉加了很多很多乙醇()大约是35wt%的量，因为最后都溶不进去了，搅拌很久)，效果并不好，做梯度测试差不多在18-25wt%左右区间是合适的

- [x] 探究一块标准肌肉20x20×50mm的各方向力学性能和某些方向形变受阻时其他方向上的力学性能
    > 最重要的是完全激活时的体积膨胀率和温度（虽然乙醇沸点为78.5°C，但是因为压力大以及加热过快各种原因，可能90°C才刚刚膨胀最大，这对应用影响很大）温度控制是解决问题的可行方法

- [ ] 其他固化方式和加工成型方法，比如说 **光固化柔性树脂**，满足高弹性高伸长率~~，生物相容性~~

- [x] 配方中加入导电填料，比如Fe粉、Cu粉，电导率要求比较高 `有用石墨烯做填料的，不过电导率不够，电阻太大`
    > 目前Ni丝加热方法不错，加热速度够快，虽然功率有点大，但是让肌肉自身导电从而发热，效果不会比电阻丝好

- [ ] 有什么其他激活剂可以用吗  `寻找不影响硅橡胶固化且与硅橡胶相溶性较好的不易挥发的无毒无害的低沸点激活剂（50°C左右）`

- [x] 升温固化（以及升温温度）和不升温固化对乙醇在硅橡胶中的残余量、结合度、力学性能的影响
    > 从应用上讲，目的就是让肌肉块受热膨胀，乙醇被锁住在橡胶里面，残余量越多越好（并不是固化前加的越多越好），不考虑升温固化，会使乙醇挥发更严重


### 加工成型
3D柔性打印：3D打印机结构现成有的，需要另设计挤出头（20171212既然做柔性挤出头，索性做一下多喷头的功能，Cura最新版支持多喷头切片，优秀）

- [x] 方案一：电机

    针筒固定，通过皮带或丝杆传动使一滑块沿着针筒方向移动，推进针管挤出原料，修正3D打印机挤出机E的步进脉冲，控制针筒出料量，远程挤出比较好，否则打印头太重了

- [ ] 方案二：气动

    现在产品化的标配，从点胶机衍生而来，一长管一头接到密封的针筒尾端，另一头通气泵，气压推动出料，优点在于可以将针筒挂在打印头上，近程挤出，而且可以打印**生物材料包括细胞**

    点胶针筒加活塞加适配器([淘宝链接][buy1] [仅供参考][buy2])

- [ ] 方案三：料筒 + 绞龙 + 微型电机

    精密配合，类似拉丝机，用来柔性挤出貌似也不错，市场上有这种产品

- [ ] 方案四：模具 + 紫外光

 实验室有3D打印用的柔性光固化树脂，但是如果掺入乙醇通过打印机来制备肌肉块，会有一个问题：那一池子掺了乙醇的树脂，用机器打印必然会剩下一些，剩下的就没法用了，这个可浪费不起，所以打算设计一个模具，把树脂混合乙醇后倒入模具，使用紫外光照射

## 设计制作机械臂
- [x] 16个自由度（拇指2个弯曲加1指根旋转，其余四指各3个弯曲，五指张扩并拢1个）会不会有点多（确实多了，10个自由度，5根指头可以弯曲伸直就够了），根据肌肉使用方法确定肌肉的形状体积，尽快建模打印
    > 最后还是做成了14个关节的(拇指2×1剩下3×4)，线驱动，一根手指一条线，伸展依靠橡皮筋拉紧，握拳依靠肌肉收缩

- [x] 控制电路
    - [x] 加热功率比较大，控电流（三极管之类），还是PWM（普通继电器应该是响应时间太长的，晶闸管？）
    - 大电流三极管即可

    - [x] 发送各肌肉目前温度到PC，找一下python的串口示波器（Serial Scope），展示效果会显得很好，根据PC的指令控制功率输出

    - [ ] 其他传感器信号反馈：训练机械手时相当于一个监督者的眼睛，还有热敏电阻反馈温度

## 温控算法和RL算法
- 神经网络（现代智能控制方法）控温算法，响应速度快，抗干扰能力强，鲁棒性高，如何建立架构，见代码
- Q-Learning、Sarsa、DQN的算法实现，相对简单，但是从串口读数据，建立数据流，实时作为算法输入，还需要完成数据接口的书写(buffer+commander)


[1688]: https://s.1688.com/selloffer/offer_search.htm?keywords=%CB%AB%D7%E9%B7%D6RTV%B9%E8%CF%F0%BD%BA&n=y&spm=a260k.635.1998096057.d1 "关键词：双组分RTV硅橡胶"

[questions]: https://github.com/hankso/SoftMuscle-Robot/blob/master/README.md#项目中碰到的问题 "项目中碰到的一些问题"

[buy1]: https://item.taobao.com/item.htm?id=522812195764&ali_refid=a3_420434_1006:1107147130:N:%E7%82%B9%E8%83%B6%E9%92%88%E7%AD%92:4cbf51b45dab76338c35622b723284cc&ali_trackid=1_4cbf51b45dab76338c35622b723284cc&spm=a230r.1.1957635.63

[buy2]: https://item.taobao.com/item.htm?id=537907350264&ali_refid=a3_420435_1006:1105494038:N:%E7%82%B9%E8%83%B6%E9%92%88%E7%AD%92:0fd66f22173eeb1ec0925bdf2ea6042e&ali_trackid=1_0fd66f22173eeb1ec0925bdf2ea6042e&spm=a230r.1.1989828.6
