# Vision & Embodied AI Research Map / 视觉与具身智能研究地图

> **作者**：林树铭  
> **单位**：广东工业大学  
> **定位**：一份面向视觉感知、空间三维、自动驾驶、具身智能与机器人方向的研究地图。  
> **目标读者**：刚进入计算机视觉、自动驾驶、具身智能、多模态、机器人等方向的研究生与初学者。  
> **核心用途**：帮助读者在拿到一篇论文后，迅速判断它属于哪类视觉/具身任务、处于哪条技术主线、连接哪些上下游系统，而不是只记住一堆孤立名词。  
> **阅读方式**：本文采用 Markdown 原生的 `<details>` / `<summary>` 折叠块。建议先看“全局速览”，再根据研究方向逐级展开感兴趣的模块。  
> **核心原则**：不要把论文名、模型名和任务名当成孤立标签，而要把它们放回“任务定义 → 方法演化 → 系统位置 → 应用场景”的技术主线中理解。

---

## How to Cite / 如何引用

```text
林树铭. Vision & Embodied AI Research Map / 视觉与具身智能研究地图. 广东工业大学, 2026.
```

## License / 使用许可

本文由作者整理撰写，供学习和研究参考。转载请注明作者与原始链接。若作为开源学习资料发布，建议采用 **CC BY-NC 4.0**：允许分享和改编，但需署名，且不得用于商业用途。


## Global Quick Overview / 全局一页速览

```text
Vision & Embodied AI Research Map / 视觉与具身智能研究地图

├── 00. How to Read / 如何阅读这张地图
│   ├── 任务 Task：论文直接解决什么问题？
│   ├── 方法 Method：论文属于哪条技术演化路线？
│   ├── 系统位置 System Role：论文服务上游还是下游？
│   ├── 应用场景 Domain：论文在哪个真实场景里有价值？
│   └── 00.1 Glossary / 常用缩写表
│
├── Part I. General Vision Core / 通用视觉核心
│   ├── 01. Image Classification & Visual Representation / 图像分类与视觉表征
│   ├── 02. Object Detection / 目标检测
│   ├── 03. Image Segmentation / 图像分割
│   └── 04. Object Tracking & Video Understanding / 目标跟踪与视频理解
│
├── Part II. Low-level, Generation & Spatial Intelligence / 低层、生成与空间智能
│   ├── 05. Image Restoration & Enhancement / 图像恢复与增强
│   ├── 06. Image Fusion & Cross-modal Fusion / 图像融合与跨模态融合
│   ├── 07. Image Generation & Editing / 图像生成与编辑
│   ├── 08. 3D Vision & 3D Reconstruction / 三维视觉与三维重建
│   ├── 09. NeRF, 3DGS & Neural Rendering / NeRF、3DGS 与神经渲染
│   └── 10. Point Cloud, BEV & Occupancy / 点云、BEV 与 Occupancy
│
├── Part III. Text, Multimodal & Open-world Perception / 文档、多模态与开放世界感知
│   ├── 11. OCR & Document Understanding / OCR 与文档理解
│   ├── 12. Multimodal Understanding / 多模态理解
│   ├── 13. Open-Vocabulary Perception / 开放世界感知
│   └── 14. VFM, MLLM & Agents / 视觉大模型与智能体
│
└── Part IV. System-level Intelligence / 系统级智能
    ├── 15. Prediction, Planning & Dynamic World Modeling / 预测、规划与动态世界建模
    ├── 16. Autonomous Driving Research Map / 自动驾驶研究地图
    ├── 17. Embodied AI Research Map / 具身智能研究地图
    └── 18. World Models & Simulation / 世界模型与仿真
```

---

<details open>
<summary><strong>00. How to Read This Map / 如何阅读这张地图</strong></summary>

这份地图的目标不是把所有名词堆成百科，而是帮新手建立一种“论文定位能力”。读任何一篇论文时，都不要先问“它用了什么模型”，而要先问：

```text
它解决什么任务？
它把什么输入变成什么输出？
它处在系统中的哪个位置？
它继承了哪条方法主线？
它为什么会在这个时间点出现？
它解决了上一代方法的什么痛点？
```

很多新手会把不同维度混在一起。例如在目标检测里：

```text
DETR-based Detection / DETR 系检测
Real-time Detection / 实时检测
Small Object Detection / 小目标检测
Remote Sensing Detection / 遥感检测
Open-vocabulary Detection / 开放词汇检测
```

这些概念并不是同一层级：DETR 是方法主线，实时是工程约束，小目标是任务难点，遥感是应用领域，开放词汇是类别开放性。本文每个模块都尽量按照以下结构组织：

```text
1. Quick Overview / 一页速览
2. Basic Definition & Task Variants / 核心定义与任务变体
3. Method Evolution / 方法演化主线
4. Upstream & Downstream / 上下游定位
5. Representative Works / 代表性工作速览
6. Paper Positioning / 论文归位指引
7. Paper Cards / 核心论文卡片
```

### 00.4 Core Positioning Principles / 核心归位原则

读者拿到一篇新论文时，只需要先判断四件事：

```text
它解决的直接任务是什么？
它主要改的是数据、表征、模型、训练目标、推理流程，还是系统接口？
它服务的上游输入和下游模块分别是什么？
它的价值是提高精度、扩大开放性、降低成本，还是让系统更可部署？
```

本文后续章节会围绕这四个问题展开，不再单独保留冗长的跨模块归位章节。

</details>

### 00.1 Glossary / 常用缩写表

| 缩写 | 全称 / 中文 | 在本文中的位置 |
|---|---|---|
| CV | Computer Vision / 计算机视觉 | 总体领域 |
| CNN | Convolutional Neural Network / 卷积神经网络 | 分类、检测、分割、低层视觉 |
| ViT | Vision Transformer / 视觉 Transformer | 视觉表征、检测、分割 |
| SSM | State Space Model / 状态空间模型 | 新型视觉 backbone |
| SSL | Self-supervised Learning / 自监督学习 | 视觉表征预训练 |
| VLM | Vision-Language Model / 视觉语言模型 | 图文对齐、多模态理解 |
| MLLM | Multimodal Large Language Model / 多模态大语言模型 | 多模态理解、视觉智能体 |
| VLA | Vision-Language-Action / 视觉-语言-动作模型 | 具身智能、机器人控制 |
| OCR | Optical Character Recognition / 光学字符识别 | 文档理解 |
| VQA | Visual Question Answering / 视觉问答 | 多模态理解 |
| REC | Referring Expression Comprehension / 指代表达理解 | 视觉定位 |
| SOT | Single Object Tracking / 单目标跟踪 | 跟踪与视频理解 |
| MOT | Multi-object Tracking / 多目标跟踪 | 跟踪与自动驾驶 |
| VOS | Video Object Segmentation / 视频目标分割 | 视频分割、SAM 2 |
| SR | Super-Resolution / 超分辨率 | 低层视觉 |
| IVIF | Infrared-Visible Image Fusion / 红外-可见光融合 | 图像融合 |
| GAN | Generative Adversarial Network / 生成对抗网络 | 图像生成、超分 |
| Diffusion | Diffusion Model / 扩散模型 | 图像生成、恢复、策略学习 |
| NeRF | Neural Radiance Fields / 神经辐射场 | 神经渲染、三维重建 |
| 3DGS | 3D Gaussian Splatting / 三维高斯泼溅 | 神经渲染、实时场景表示 |
| SLAM | Simultaneous Localization and Mapping / 同步定位与建图 | 三维与机器人 |
| MVS | Multi-view Stereo / 多视角立体 | 三维重建 |
| BEV | Bird's-eye View / 鸟瞰图表征 | 自动驾驶、三维感知 |
| Occupancy | Occupancy Prediction / 三维占据预测 | 自动驾驶、世界模型 |
| HD Map | High-definition Map / 高精地图 | 自动驾驶 |
| VLN | Vision-Language Navigation / 视觉语言导航 | 具身智能 |
| BC | Behavior Cloning / 行为克隆 | 机器人策略学习 |
| RL | Reinforcement Learning / 强化学习 | 机器人、世界模型 |
| IL | Imitation Learning / 模仿学习 | 机器人学习 |
| RPN | Region Proposal Network / 区域候选网络 | Faster R-CNN、两阶段目标检测 |
| FPN | Feature Pyramid Network / 特征金字塔网络 | 检测、分割、多尺度特征 |
| DETR | Detection Transformer / 基于 Transformer 的集合预测检测器 | 目标检测、开放词汇检测 |
| VLP | Vision-Language Pretraining / 视觉语言预训练 | 多模态理解 |
| MAE | Masked Autoencoders / 掩码自编码器 | 自监督视觉表征、视觉基础模型 |
| DINO | Self-Distillation with No Labels / 无标签自蒸馏；也需与 DETR-DINO 区分 | 自监督视觉表征、目标检测 |
| DiT | Diffusion Transformer / 扩散 Transformer | 图像生成、视频生成、世界模型 |
| CVAE | Conditional Variational Autoencoder / 条件变分自编码器 | 轨迹预测、生成式预测 |
| MPC | Model Predictive Control / 模型预测控制 | 规划、控制、机器人 |
| POMDP | Partially Observable Markov Decision Process / 部分可观测马尔可夫决策过程 | 决策、规划、自动驾驶 |
| GUI Agent | Graphical User Interface Agent / 图形界面智能体 | 视觉智能体 |

---


### 00.2 Paper Cards Navigation / 论文卡片导航规则

本文采用“**正文自然阅读 + 章节代表工作表 + 章节 Paper Cards**”的论文链接方式：

```text
正文与一页速览：只写自然方法名，不塞入 #paper 锚点
Representative Works：只提供宏观时间线与方法位置
Paper Cards：集中提供 Title / Year / Core Contribution / Links
全局索引：删除，避免文末重复堆砌
```

这样读者阅读主线时不会被索引符号打断；真正需要打开论文时，再进入对应章节末尾的 Paper Cards。

---

## Part I. General Vision Core / 通用视觉核心

### 01. Image Classification & Visual Representation / 图像分类与视觉表征

<details open>
<summary><strong>01.0 Quick Overview / 一页速览</strong></summary>

```text
Image Classification & Visual Representation / 图像分类与视觉表征

├── 任务本质：把图像映射到语义类别，或学习可迁移的视觉特征
├── 输入：图像 / 视频帧 / 图文对 / 大规模无标注图像
├── 输出：类别标签、概率分布、embedding、可迁移视觉表征
├── 下游：检测、分割、跟踪、检索、多模态、自动驾驶、具身智能
│
├── 方法演化主线
│   ├── 手工特征时代：SIFT / HOG / BoVW
│   ├── CNN 监督学习时代：AlexNet → VGG / GoogLeNet → ResNet → EfficientNet / ConvNeXt
│   ├── Transformer 视觉 backbone 时代：ViT → DeiT → Swin Transformer
│   ├── 自监督表征时代：MoCo / SimCLR → BYOL / DINO → MAE → DINOv2
│   ├── 图文对齐时代：CLIP / ALIGN / SigLIP
│   └── 新型序列建模时代：Vision Mamba / VMamba
│
└── 新手核心理解
    分类不是“最简单的视觉任务”这么简单，它是很多视觉系统的 backbone 训练场。
```

</details>

<details>
<summary><strong>01.1 Basic Definition & Task Variants / 核心定义与任务变体</strong></summary>

**Image Classification / 图像分类** 最原始的问题是：给一张图像，判断它属于哪个类别。

```text
Input / 输入：一张图像
Output / 输出：类别标签或类别概率
Example / 例子：dog 0.91, cat 0.06, wolf 0.03
```

但在现代视觉研究里，图像分类的意义已经远远超过“给图贴标签”。它更像是视觉表征学习的基础训练场：一个模型如果能在大规模图像上学到好的视觉特征，这些特征可以迁移到检测、分割、跟踪、深度估计、姿态估计、多模态理解等下游任务。

所以，新手不要把分类理解成“过时任务”。更准确地说：

> 分类任务本身可能不复杂，但分类预训练得到的视觉表征，是现代视觉系统的重要基础设施。

</details>

<details>
<summary><strong>01.2 Method Evolution / 方法演化主线</strong></summary>

<details open>
<summary><strong>01.2.1 From Hand-crafted Features to CNN / 从手工特征到 CNN</strong></summary>

早期图像分类依赖人工设计特征，例如 SIFT、HOG、LBP、BoVW。研究者先设计“图像里什么局部模式重要”，再用 SVM 或其他分类器做分类。

CNN 时代改变了这件事：模型不再依赖人手设计特征，而是通过数据端到端学习特征。AlexNet 是一个分水岭：它在 ImageNet 上展示了深度卷积网络相对于传统方法的巨大优势，也让大规模数据、GPU 训练、ReLU、Dropout 等工程组件成为视觉模型训练的关键基础。

之后，CNN 主线大致沿着两个方向推进：

```text
更深：AlexNet → VGG → ResNet
更高效：GoogLeNet / Inception → MobileNet → EfficientNet
更现代化：ResNet → ConvNeXt
```

ResNet 的关键不是“又堆深了网络”，而是通过残差连接缓解深层网络训练退化，使得几十层、上百层网络可以稳定优化。ConvNeXt 则代表了一个很有意思的回摆：在 Transformer 流行之后，研究者重新审视 CNN 设计，把许多现代化训练和结构设计吸收回卷积网络，证明纯 CNN 仍然可以在视觉 backbone 中保持竞争力。

</details>

<details>
<summary><strong>01.2.2 Vision Transformer Era / 视觉 Transformer 时代</strong></summary>

ViT 把图像切成 patch，把每个 patch 当作 token，然后用 Transformer 做全局建模。它的思想很简单，但影响很大：

```text
图像不一定只能用卷积处理，也可以被看成 token 序列。
```

ViT 的缺点也很明显：它对数据量和训练策略很敏感，在小数据集上未必天然优于 CNN。DeiT 通过更好的训练策略和蒸馏方法，让 ViT 在 ImageNet 规模上更容易训练。Swin Transformer 则进一步引入层次化结构和窗口注意力，让 Transformer 更适合检测、分割等密集预测任务。

新手可以这样理解三者关系：

```text
ViT：证明 Transformer 可以做图像分类
DeiT：证明 ViT 可以在更常规的数据规模上训练好
Swin：把 Transformer 做成通用视觉 backbone，服务检测和分割
```

</details>

<details>
<summary><strong>01.2.3 Self-supervised Representation / 自监督视觉表征</strong></summary>

自监督学习的核心目标是：减少对人工标签的依赖，让模型从图像本身学习有用表征。

早期主线包括对比学习：

```text
SimCLR / MoCo：让同一张图的不同增强视图更接近，不同图像更远
BYOL：不显式使用负样本，也能学习表征
DINO：自蒸馏 + ViT，出现了很强的语义区域感知能力
MAE：随机遮掉大量 patch，让模型重建缺失内容
DINOv2：通过更大规模、更干净的数据和更稳定训练，学习通用视觉特征
```

这里有一个很关键的观念变化：

> 视觉表征不一定来自“分类标签监督”，也可以来自图像自身的结构、视图一致性、遮挡重建、图文对齐。

这条线对后续检测、分割、3D、机器人都很重要，因为很多下游领域缺标注，依赖自监督或基础模型特征迁移。

</details>

<details>
<summary><strong>01.2.4 Vision-Language Representation / 视觉语言表征</strong></summary>

CLIP 让图像分类从“固定类别分类器”变成了“图像和文本的语义对齐”。它训练图像编码器和文本编码器，让匹配的图文对更接近，不匹配的更远。这样，分类时可以直接用文本提示：

```text
"a photo of a dog"
"a photo of a cat"
"a photo of a traffic light"
```

然后比较图像和各个文本提示的相似度。

这带来的影响非常大：

```text
传统分类：只能识别训练集里的固定类别
CLIP 式分类：可以用文本描述新类别，实现 zero-shot / open-vocabulary
```

后来的开放词汇检测、开放词汇分割、文本引导图像生成、视觉语言导航、具身任务理解，都与这种图文对齐表征有关。

</details>

<details>
<summary><strong>01.2.5 Vision Mamba & State Space Models / Vision Mamba 与状态空间模型</strong></summary>

Mamba / State Space Model 进入视觉领域，主要动机不是“替代一切 Transformer”，而是尝试在长序列、高分辨率视觉输入中获得更好的效率和全局建模能力。

视觉任务和语言不同：图像是二维结构，不是天然的一维序列。因此 Vision Mamba 类方法通常需要解决两个问题：

```text
1. 如何把二维图像合理扫描成序列？
2. 如何在保持效率的同时建模局部与全局关系？
```

VMamba 的代表性设计是 2D Selective Scan，通过多个方向扫描图像，缓解一维扫描和二维视觉结构之间的不匹配。对于新手而言，可以把 Vision Mamba 暂时放在“新型视觉 backbone”位置上理解，而不是把它当成独立任务。

</details>

</details>

<details>
<summary><strong>01.3 Upstream & Downstream / 上下游定位</strong></summary>

分类与视觉表征通常是视觉系统的基础特征层。

```text
上游输入：图像、视频帧、图文对或大规模无标注图像
本章输出：类别概率、embedding、backbone feature、图文对齐特征
下游模块：检测、分割、跟踪、检索、开放词汇感知、多模态理解、3D 与机器人策略
系统价值：提供可迁移的视觉表征，而不是只完成“整图分类”
```

</details>

<details>
<summary><strong>01.4 Representative Works / 代表性工作速览</strong></summary>

| 年份 / Year | 方法 / Work | 位置 / Position | 为什么重要 / Why it matters |
|---:|---|---|---|
| 1999-2005 | SIFT / HOG / BoVW | 手工特征 | CNN 前时代的核心局部特征与视觉词袋思想 |
| 2012 | AlexNet, *ImageNet Classification with Deep Convolutional Neural Networks* | 深度 CNN 起点 | 让深度卷积网络成为视觉识别主流 |
| 2014 | VGG / GoogLeNet | CNN 加深与结构设计 | VGG 强调简单堆叠，GoogLeNet 强调 Inception 多尺度结构 |
| 2015 | ResNet, *Deep Residual Learning for Image Recognition* | 深层 CNN | 残差连接解决深层网络退化问题 |
| 2017-2019 | MobileNet / EfficientNet | 高效 CNN | 面向移动端和效率的 CNN 设计 |
| 2020 | ViT, *An Image is Worth 16x16 Words* | 视觉 Transformer | 把图像 patch 化并用 Transformer 建模 |
| 2021 | DeiT | 可训练 ViT | 通过蒸馏和训练策略让 ViT 更易用 |
| 2021 | Swin Transformer | 层次化 Transformer | 让 Transformer 成为检测、分割可用的通用 backbone |
| 2021 | CLIP | 图文对齐 | 让自然语言成为视觉分类和开放词汇识别的接口 |
| 2021 | DINO | 自监督 ViT | 自监督 ViT 出现显著语义区域感知能力 |
| 2021 | MAE | 掩码图像建模 | 用遮挡重建训练可扩展视觉表征 |
| 2022 | ConvNeXt | 现代化 CNN | 重新证明 CNN 在现代训练配方下仍有竞争力 |
| 2023 | DINOv2 | 视觉基础特征 | 学习可迁移、通用的自监督视觉特征 |
| 2024 | VMamba | 视觉状态空间模型 | 把 Mamba / SSM 引入视觉 backbone |

</details>

<details>
<summary><strong>01.5 Paper Positioning / 论文归位指引</strong></summary>

读分类或视觉表征论文时，优先判断它改的是哪一层：

```text
1. Architecture / 结构：CNN、Transformer、Mamba、Hybrid？
2. Pretraining / 预训练：监督、自监督、图文对齐、掩码建模？
3. Data / 数据：ImageNet、私有大规模数据、图文对、领域数据？
4. Transfer / 迁移：只做分类，还是服务检测、分割、3D、机器人？
5. Efficiency / 效率：是否面向边缘端、高分辨率、长序列？
```

例如：

```text
一篇“Vision Mamba for Remote Sensing Classification”的论文
主归属：图像分类与视觉表征
方法标签：Mamba / State Space Model
应用标签：遥感
核心问题：高分辨率遥感图像的长程依赖和效率
下游关联：遥感检测、变化检测、地物分割
```

</details>

<details>
<summary><strong>01.6 Paper Cards / 核心论文卡片</strong></summary>

> 本节集中放置本章代表论文入口。正文和代表论文表格中的方法名优先跳转到这里，外部 Paper / Code / Project 链接只在论文卡片中出现。

<a id="paper-01-alexnet"></a>

#### AlexNet

- **Title / 标题**：AlexNet, ImageNet Classification with Deep Convolutional Neural Networks
- **Year / 年份**：2012
- **Core Contribution / 核心贡献**：在 ImageNet 上证明大规模深度 CNN 的有效性，推动视觉识别进入深度学习阶段。
- **Links / 链接**：[Paper](https://proceedings.neurips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf)
<a id="paper-01-resnet"></a>

#### ResNet

- **Title / 标题**：ResNet, Deep Residual Learning for Image Recognition
- **Year / 年份**：2015
- **Core Contribution / 核心贡献**：提出残差连接以缓解深层网络退化问题，使超深 CNN 可以稳定训练。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1512.03385)
<a id="paper-01-vit"></a>

#### ViT

- **Title / 标题**：ViT, An Image is Worth 16x16 Words
- **Year / 年份**：2020
- **Core Contribution / 核心贡献**：将图像切分为 patch token 并用 Transformer 建模，开创视觉 Transformer 路线。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2010.11929)
<a id="paper-01-swin-transformer"></a>

#### Swin Transformer

- **Title / 标题**：Swin Transformer
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：提出层次化窗口注意力结构，使 Transformer 更适合检测、分割等密集预测任务。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2103.14030)
<a id="paper-01-clip"></a>

#### CLIP

- **Title / 标题**：CLIP
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：通过大规模图文对比学习建立开放词汇视觉语义空间。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2103.00020)
<a id="paper-01-dino"></a>

#### DINO

- **Title / 标题**：DINO
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：用自蒸馏训练 ViT，使自监督模型涌现出显著的语义区域感知能力。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2104.14294)
<a id="paper-01-mae"></a>

#### MAE

- **Title / 标题**：MAE
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：用高比例随机遮挡与重建训练可扩展视觉表征，推动 masked image modeling 成为主流预训练范式。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2111.06377)
<a id="paper-01-convnext"></a>

#### ConvNeXt

- **Title / 标题**：ConvNeXt
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：用现代训练策略和结构设计重塑纯 CNN，证明卷积网络仍可作为强视觉 backbone。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2201.03545)
<a id="paper-01-dinov2"></a>

#### DINOv2

- **Title / 标题**：DINOv2
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：通过大规模自监督训练获得强迁移视觉特征，代表视觉基础表征路线。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2304.07193)
<a id="paper-01-vmamba"></a>

#### VMamba

- **Title / 标题**：VMamba
- **Year / 年份**：2024
- **Core Contribution / 核心贡献**：将选择性状态空间模型引入视觉 backbone，探索高分辨率长序列视觉建模的新路线。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2401.10166)
</details>

### 02. Object Detection / 目标检测

<details open>
<summary><strong>02.0 Quick Overview / 一页速览</strong></summary>

```text
Object Detection / 目标检测

├── 任务本质：判断图像里有哪些物体，以及每个物体在哪里
├── 输入：RGB / 视频 / 红外 / RGB-D / LiDAR / Radar / 高光谱 / 文本提示
├── 输出：类别 class + 框 box + 置信度 score
├── 下游：跟踪、分割、关系理解、轨迹预测、规划、机器人操作
│
├── 方法主线
│   ├── 传统：Haar / HOG / DPM
│   ├── 两阶段 CNN：R-CNN → Fast R-CNN → Faster R-CNN → Mask R-CNN / Cascade R-CNN
│   ├── 一阶段 CNN：YOLO → SSD → RetinaNet
│   ├── Anchor-free：FCOS → CenterNet
│   ├── DETR：DETR → Deformable DETR → DINO → RT-DETR → D-FINE → DEIM
│   └── 开放词汇：GLIP → OWL-ViT / OWLv2 → Grounding DINO → Grounding DINO 1.5 → DINO-X
│
├── 任务变体
│   ├── 小目标 / 遮挡 / 伪装 / 密集 / 长尾 / 开放世界
│   ├── 水平框 / 旋转框 / 3D 框 / 非模态框
│   └── RGB-T / RGB-D / LiDAR-Camera / Radar-Camera / Event / Hyperspectral
│
└── 新手核心理解
    目标检测不是单一技术名词，而是“检测流程、类别开放性、输入模态、工程约束、应用领域”的交叉点。
```

</details>

<details>
<summary><strong>02.1 Basic Definition & Task Variants / 核心定义与任务变体</strong></summary>

目标检测回答两个问题：

```text
1. What / 是什么：图像里有哪些目标类别？
2. Where / 在哪里：每个目标的位置在哪里？
```

典型输出为：

```text
person: [x1, y1, x2, y2], score=0.97
car:    [x1, y1, x2, y2], score=0.93
```

目标检测和分类、分割、跟踪的区别：

| 任务 | 输出 | 新手理解 |
|---|---|---|
| 分类 Classification | 整图类别 | 这张图是什么？ |
| 检测 Detection | 类别 + 框 | 图里有哪些东西，在哪里？ |
| 分割 Segmentation | 像素级 mask | 物体精确轮廓是什么？ |
| 跟踪 Tracking | 跨帧 ID + 位置 | 同一个物体怎么移动？ |
| 视觉定位 Grounding | 文本指代区域 | “穿红衣服的人”在哪里？ |

#### Task Variants / 任务变体

目标检测的变体不要混成一棵树，而要按维度理解。

#### 02.1.1 By Geometry / 按几何输出

```text
Horizontal Bounding Box / 水平框：自然图像最常见
Oriented Bounding Box / 旋转框：遥感、文本、工业零件
3D Bounding Box / 三维框：自动驾驶、机器人
Amodal Box / 非模态框：预测被遮挡物体的完整范围
Keypoint-based Box / 关键点框：通过中心点、角点等表示目标
```

#### 02.1.2 By Challenge / 按任务难点

```text
Small Object Detection / 小目标检测
Tiny Object Detection / 微小目标检测
Dense Object Detection / 密集目标检测
Occluded Object Detection / 遮挡目标检测
Camouflaged Object Detection / 伪装目标检测
Long-tail Detection / 长尾检测
Open-world Detection / 开放世界检测
Domain-adaptive Detection / 域适应检测
```

#### 02.1.3 By Domain / 按应用领域

```text
Autonomous Driving Detection / 自动驾驶检测
Remote Sensing Detection / 遥感检测
Medical Lesion Detection / 医学病灶检测
Industrial Defect Detection / 工业缺陷检测
Document Element Detection / 文档元素检测
Underwater Object Detection / 水下目标检测
Agricultural Detection / 农业检测
Robotics Object Detection / 机器人目标检测
```

#### 02.1.4 By Supervision / 按监督方式

```text
Fully-supervised Detection / 全监督检测
Semi-supervised Detection / 半监督检测
Weakly-supervised Detection / 弱监督检测
Few-shot Detection / 小样本检测
Zero-shot Detection / 零样本检测
Open-vocabulary Detection / 开放词汇检测
Unsupervised Object Discovery / 无监督目标发现
```

#### 02.1.5 By Modality / 按输入模态

多模态检测不是“检测器多加一个输入”这么简单。它关心不同传感器之间如何互补：

```text
RGB：语义强，受光照影响大
Infrared / Thermal：夜间和弱光更稳定，但纹理少
Depth / LiDAR：几何和距离准确，但稀疏或成本高
Radar：速度和恶劣天气鲁棒性好，但空间分辨率低
Event Camera：高动态范围、低延迟，但数据形式特殊
Hyperspectral：光谱信息丰富，但维度高、标注少
Text：提供类别和语义约束
```

常见分支：

| 分支 | 输入 | 典型场景 | 核心难点 |
|---:|---|---|---|
| RGB-T Detection / RGB-热红外检测 | 可见光 + 热红外 | 夜间行人、安防 | 模态对齐、光照差异、热源干扰 |
| RGB-D Detection / RGB-D 检测 | RGB + 深度 | 室内机器人、抓取 | 深度噪声、遮挡、几何融合 |
| LiDAR-Camera Detection / 激光雷达-相机检测 | 点云 + 图像 | 自动驾驶 3D 检测 | 标定误差、稀疏点云、BEV 融合 |
| Radar-Camera Detection / 雷达-相机检测 | 雷达 + 图像 | 恶劣天气驾驶 | 雷达稀疏、虚警、时间同步 |
| Event-based Detection / 事件相机检测 | 事件流 | 高速运动、低延迟 | 异步数据、事件表征 |
| Hyperspectral Detection / 高光谱检测 | 光谱图像 | 遥感、农业、军事 | 高维光谱、少样本、小目标 |
| Language-guided Detection / 语言引导检测 | 图像 + 文本 | 开放词汇、机器人 | 视觉语义对齐、指代表达歧义 |

在自动驾驶里，TransFusion、BEVFusion 等工作可以放在多模态 3D 检测和 BEV 表征的交叉位置。它们不是普通 2D 检测器，而是在解决“多传感器信息如何统一为空间表征并服务 3D 检测”的问题。

</details>

<details>
<summary><strong>02.2 Method Evolution / 方法演化主线</strong></summary>

<details open>
<summary><strong>02.2.1 Traditional Detection / 传统检测：滑窗、特征、分类器</strong></summary>

传统检测的基本思路是：在图像中枚举大量候选窗口，对每个窗口提取特征，再用分类器判断是不是目标。

```text
滑动窗口 → 手工特征 → 分类器 → 后处理
```

代表路线包括 Haar + AdaBoost（人脸检测）、HOG + SVM（行人检测）、DPM（可变形部件模型）。这一阶段的核心问题是：特征由人设计，系统很难端到端优化，复杂场景泛化能力有限。

</details>

<details>
<summary><strong>02.2.2 Two-stage CNN Detectors / 两阶段 CNN 检测器</strong></summary>

两阶段检测器把检测拆成两步：

```text
第一阶段：找可能有物体的候选区域 Region Proposals
第二阶段：对候选区域分类和回归框
```

技术主线：

```text
R-CNN → Fast R-CNN → Faster R-CNN → Mask R-CNN → Cascade R-CNN
```

- **R-CNN**：用 CNN 提取候选区域特征，开启深度检测时代，但速度慢。
- **Fast R-CNN**：共享整图特征，减少重复计算。
- **Faster R-CNN**：引入 RPN，让候选区域生成也由网络学习。
- **Mask R-CNN**：在检测框基础上增加 mask 分支，连接检测和实例分割。
- **Cascade R-CNN**：通过多阶段逐步提高 IoU 质量，提升高质量定位。

新手理解：两阶段方法通常精度强、结构清晰，但实时性不如轻量一阶段检测器。

</details>

<details>
<summary><strong>02.2.3 One-stage CNN Detectors / 一阶段 CNN 检测器</strong></summary>

一阶段检测器直接在特征图上预测类别和框，不再显式生成 proposal。

```text
图像 → Backbone → Neck → Detection Head → 类别 + 框
```

代表路线：

```text
YOLO → SSD → RetinaNet → YOLOv3/v4/v5/v7/v8/v9/v10/YOLO11 等工程化系列
```

一阶段检测的优势是速度快，适合实时场景。它的难点是正负样本极度不平衡，所以 RetinaNet 提出了 Focal Loss，让模型更关注难样本。

YOLO 系列本身既是学术路线，也是工程路线。对新手而言，不必把每个 YOLO 版本都当成“范式革命”，应重点理解：YOLO 系长期围绕速度、部署、训练策略、标签分配、neck/head 设计、NMS 或端到端后处理等问题迭代。

</details>

<details>
<summary><strong>02.2.4 Anchor-free Detection / 无锚框检测</strong></summary>

Anchor-based 方法需要预先设计大量 anchor box。Anchor-free 方法试图减少这种人工先验，把目标检测转成点、中心或边界距离预测。

代表路线：

```text
CornerNet：用角点表示目标
CenterNet：用中心点表示目标
FCOS：把检测转成逐像素分类 + 边界距离回归
```

新手可以这样理解：

> Anchor-free 不是简单“不要 anchor”，而是重新设计“什么位置负责预测哪个目标”的标签分配和几何表示方式。

</details>

<details>
<summary><strong>02.2.5 DETR Family / DETR 系列：从集合预测到实时 DETR</strong></summary>

DETR 的核心贡献是把目标检测改写成 **set prediction / 集合预测**：模型直接输出一组对象，通过 Hungarian matching 与真值框一对一匹配，从而减少 anchor、NMS 等人工设计。

```text
DETR：检测 = 一组对象 query 的集合预测
```

但原始 DETR 有明显问题：训练收敛慢，小目标表现弱，多尺度特征利用不足。

于是 DETR 系的发展主线大致是：

```text
DETR
→ Deformable DETR：多尺度可变形注意力，改善收敛和小目标
→ DAB-DETR / DN-DETR：改 query 设计与去噪训练
→ DINO：整合 contrastive denoising、mixed query selection、look-forward-twice box prediction
→ RT-DETR：把 DETR 推向实时检测
→ D-FINE：重定义 DETR 的边界框回归为细粒度分布精修
→ DEIM：改进 matching，用 Dense O2O matching 缓解监督稀疏、加快收敛
```

这条线的核心不是“用了 Transformer”，而是：

```text
检测问题如何从密集候选框预测，转变成对象级 query 的集合预测？
```

</details>

<details>
<summary><strong>02.2.6 Open-vocabulary Detection / 开放词汇检测</strong></summary>

传统检测器只能检测训练集里定义好的类别。开放词汇检测的目标是：给定文本类别名或指代表达，检测训练时未必见过的类别。

代表路线：

```text
CLIP-style vision-language representation
→ GLIP：统一 object detection 和 phrase grounding
→ OWL-ViT / OWLv2：基于图文预训练的开放词汇检测
→ Grounding DINO：DINO 检测器 + grounded pretraining
→ Grounding DINO 1.5：更强开放集合检测能力与部署版本
→ DINO-X：object-centric open-world vision model
```

开放词汇检测的意义在于：

```text
过去：检测器输出固定类别列表
现在：用户可以用语言指定要找什么
```

这让检测和多模态理解、机器人语言指令、开放世界感知、数据自动标注产生强关联。

</details>

</details>

<details>
<summary><strong>02.3 Upstream & Downstream / 上下游定位</strong></summary>

目标检测在视觉系统中通常处于“从图像特征到对象级结构”的中间层。

```text
上游输入：图像 / 视频帧 / 多模态传感器 / 文本提示 / backbone 特征
本章输出：类别、位置框、置信度、开放词汇 grounding 结果
下游模块：跟踪、实例分割、关系理解、轨迹预测、规划、机器人抓取、自动标注
系统价值：把连续像素转换成可被后续模块引用的对象列表
```

读检测论文时要区分两类价值：一种是作为独立感知模块提高检测精度或速度，另一种是作为下游系统的对象接口，例如 MOT、Grounded-SAM、自动驾驶预测规划或机器人语言指令执行。

</details>

<details>
<summary><strong>02.4 Representative Works / 代表性工作速览</strong></summary>

| 年份 / Year | 方法 / Work | 位置 / Position | 为什么重要 / Why it matters |
|---:|---|---|---|
| 2001 | Viola-Jones | 传统人脸检测 | Haar + AdaBoost + cascade 的经典实时检测系统 |
| 2005 | HOG + SVM | 传统行人检测 | 行人检测中的经典手工特征路线 |
| 2010 | DPM | 部件模型 | CNN 前目标检测的重要代表 |
| 2014 | R-CNN | CNN 检测起点 | 把 CNN 特征引入 region proposal 检测 |
| 2015 | Fast R-CNN | 两阶段加速 | 共享卷积特征，提高效率 |
| 2015 | Faster R-CNN | RPN | 让 proposal 生成也变成可学习模块 |
| 2016 | YOLO | 一阶段实时检测 | 把检测表述为单次前向预测 |
| 2016 | SSD | 一阶段多尺度检测 | 多尺度特征图直接预测框 |
| 2017 | RetinaNet | Focal Loss | 解决一阶段检测正负样本不平衡 |
| 2017 | Mask R-CNN | 检测 + 实例分割 | 增加 mask 分支，连接检测与分割 |
| 2019 | FCOS | Anchor-free | 逐像素预测边界距离，减少 anchor 设计 |
| 2020 | DETR | 集合预测 | 用 Transformer + Hungarian matching 重构检测范式 |
| 2020 | Deformable DETR | 多尺度 DETR | 改善 DETR 收敛和小目标问题 |
| 2022 | DINO | DETR 改进集成 | 去噪训练、query selection、box prediction 改进 |
| 2023 | RT-DETR | 实时 DETR | 把 DETR 推向实时目标检测 |
| 2024/2025 | D-FINE | 实时 DETR 定位精修 | 用 FDR 和 GO-LSD 改进 DETR 边界框回归 |
| 2025 | DEIM | DETR matching 改进 | 用 Dense O2O matching 和 Matchability-Aware Loss 加速收敛 |
| 2021 | GLIP | 语言 grounding + 检测 | 统一检测与短语定位 |
| 2022 | OWL-ViT | 开放词汇检测 | 基于图文预训练的开放词汇检测 |
| 2023 | Grounding DINO | 文本引导检测 | DINO 检测器与 grounded pretraining 结合 |
| 2024 | Grounding DINO 1.5 / DINO-X | 开放世界检测 | 面向更强开放集合与 object-centric 视觉模型 |
| 2022 | TransFusion / BEVFusion | 多模态 3D 检测 | 自动驾驶 LiDAR-camera 融合和 BEV 表征关键路线 |

</details>

<details>
<summary><strong>02.5 Paper Positioning / 论文归位指引</strong></summary>

目标检测论文优先判断以下维度：

```text
1. 它是普通 closed-set 检测，还是 open-vocabulary / open-world 检测？
2. 它改的是 backbone、neck、head、loss、label assignment、matching，还是 post-processing？
3. 它的输入是 RGB，还是 RGB-T、LiDAR-camera、hyperspectral、event、text？
4. 它追求的是精度、实时、轻量化、小目标、跨域，还是标注效率？
5. 它是否服务某个系统下游，例如自动驾驶、机器人、遥感、医学？
```

例子：

```text
Paper: D-FINE
主任务：Object Detection / 目标检测
方法主线：DETR Family → Real-time DETR
核心创新：Bounding box regression 被重新定义为 fine-grained distribution refinement
解决问题：实时 DETR 的定位精度和速度-精度平衡
```

```text
Paper: Grounding DINO
主任务：Object Detection / 目标检测
交叉任务：Visual Grounding / Open-vocabulary Perception
核心创新：文本条件下的开放集合目标定位
下游价值：自动标注、Grounded-SAM、机器人语言指令感知
```

```text
Paper: BEVFusion
主任务：Multimodal 3D Detection / 多模态三维检测
交叉任务：BEV Representation / 自动驾驶感知
核心问题：Camera、LiDAR 等多模态如何在统一 BEV 空间融合
```

</details>

<details>
<summary><strong>02.6 Paper Cards / 核心论文卡片</strong></summary>

> 本节集中放置本章代表论文入口。正文和代表论文表格中的方法名优先跳转到这里，外部 Paper / Code / Project 链接只在论文卡片中出现。

<a id="paper-02-r-cnn"></a>

#### R-CNN

- **Title / 标题**：R-CNN
- **Year / 年份**：2014
- **Core Contribution / 核心贡献**：将 CNN 特征引入候选区域检测，开启深度学习目标检测路线。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1311.2524)
<a id="paper-02-fast-r-cnn"></a>

#### Fast R-CNN

- **Title / 标题**：Fast R-CNN
- **Year / 年份**：2015
- **Core Contribution / 核心贡献**：通过共享整图卷积特征显著减少 R-CNN 的重复计算。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1504.08083)
<a id="paper-02-faster-r-cnn"></a>

#### Faster R-CNN

- **Title / 标题**：Faster R-CNN
- **Year / 年份**：2015
- **Core Contribution / 核心贡献**：提出 RPN，使候选框生成成为可学习的端到端检测模块。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1506.01497)
<a id="paper-02-yolo"></a>

#### YOLO

- **Title / 标题**：YOLO
- **Year / 年份**：2016
- **Core Contribution / 核心贡献**：将目标检测表述为单次前向预测，奠定实时一阶段检测路线。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1506.02640)
<a id="paper-02-ssd"></a>

#### SSD

- **Title / 标题**：SSD
- **Year / 年份**：2016
- **Core Contribution / 核心贡献**：在多尺度特征图上直接预测目标框，提升一阶段检测对尺度变化的处理能力。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1512.02325)
<a id="paper-02-retinanet"></a>

#### RetinaNet

- **Title / 标题**：RetinaNet
- **Year / 年份**：2017
- **Core Contribution / 核心贡献**：提出 Focal Loss 缓解一阶段检测中的正负样本不平衡。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1708.02002)
<a id="paper-02-mask-r-cnn"></a>

#### Mask R-CNN

- **Title / 标题**：Mask R-CNN
- **Year / 年份**：2017
- **Core Contribution / 核心贡献**：在检测框基础上加入 mask 分支，统一目标检测与实例分割。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1703.06870)
<a id="paper-02-fcos"></a>

#### FCOS

- **Title / 标题**：FCOS
- **Year / 年份**：2019
- **Core Contribution / 核心贡献**：将检测改写为逐像素分类与边界距离回归，减少 anchor 设计依赖。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1904.01355)
<a id="paper-02-detr"></a>

#### DETR

- **Title / 标题**：DETR
- **Year / 年份**：2020
- **Core Contribution / 核心贡献**：用对象查询、集合预测和 Hungarian matching 重构端到端目标检测范式。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2005.12872)
<a id="paper-02-deformable-detr"></a>

#### Deformable DETR

- **Title / 标题**：Deformable DETR
- **Year / 年份**：2020
- **Core Contribution / 核心贡献**：提出多尺度可变形注意力，缓解 DETR 收敛慢和小目标弱的问题。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2010.04159)
<a id="paper-02-dino"></a>

#### DINO

- **Title / 标题**：DINO
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：整合去噪训练、query selection 与框预测改进，提升 DETR 系检测器的收敛和精度。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2203.03605)
<a id="paper-02-rt-detr"></a>

#### RT-DETR

- **Title / 标题**：RT-DETR
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：将 DETR 系检测器推向实时部署，减少端到端检测与工程实时性的鸿沟。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2304.08069)
<a id="paper-02-d-fine"></a>

#### D-FINE

- **Title / 标题**：D-FINE
- **Year / 年份**：2024/2025
- **Core Contribution / 核心贡献**：用细粒度分布精修重新建模 DETR 边界框回归，提高实时检测定位质量。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2410.13842)
<a id="paper-02-deim"></a>

#### DEIM

- **Title / 标题**：DEIM
- **Year / 年份**：2025
- **Core Contribution / 核心贡献**：通过改进匹配策略增强密集监督，提升 DETR 训练收敛速度。
- **Links / 链接**：[Paper](https://openaccess.thecvf.com/content/CVPR2025/html/Huang_DEIM_DETR_with_Improved_Matching_for_Fast_Convergence_CVPR_2025_paper.html)
<a id="paper-02-glip"></a>

#### GLIP

- **Title / 标题**：GLIP
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：将目标检测与短语 grounding 统一为 grounded language-image pretraining。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2112.03857)
<a id="paper-02-grounding-dino"></a>

#### Grounding DINO

- **Title / 标题**：Grounding DINO
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：把 DINO 检测器与 grounded pretraining 结合，实现文本条件开放集合检测。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2303.05499)
<a id="paper-02-dino-x"></a>

#### DINO-X

- **Title / 标题**：DINO-X
- **Year / 年份**：2024
- **Core Contribution / 核心贡献**：面向开放世界对象感知构建 object-centric 视觉模型，扩展开放集合检测能力。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2411.14347)
<a id="paper-02-bevfusion"></a>

#### BEVFusion

- **Title / 标题**：BEVFusion
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：在统一 BEV 空间融合多传感器特征，提升自动驾驶三维感知。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2205.13542)
</details>

### 03. Image Segmentation / 图像分割

<details open>
<summary><strong>03.0 Quick Overview / 一页速览</strong></summary>

```text
Image Segmentation / 图像分割

├── 任务本质：把图像从“框级对象”进一步细化到“像素级区域”
├── 输入：RGB / 医学图像 / 遥感图像 / 视频 / 文本提示 / 点击提示 / 框提示
├── 输出：pixel label / object mask / instance mask / panoptic map
│
├── 主要任务
│   ├── Semantic Segmentation / 语义分割：每个像素属于什么类别
│   ├── Instance Segmentation / 实例分割：每个独立对象的 mask
│   ├── Panoptic Segmentation / 全景分割：thing + stuff 统一
│   ├── Referring Segmentation / 指代表达分割：文本指代对象的 mask
│   ├── Interactive Segmentation / 交互式分割：点击、框、scribble 提示
│   └── Video Segmentation / 视频分割：跨帧一致的对象 mask
│
├── 方法主线
│   ├── FCN → U-Net / SegNet → DeepLab / PSPNet / HRNet
│   ├── Transformer：SETR → SegFormer
│   ├── Universal：MaskFormer → Mask2Former → OneFormer
│   ├── Promptable：SAM → SAM 2
│   └── Open-vocabulary：CLIP-based segmentation / X-Decoder / SEEM / Grounded-SAM
│
└── 新手核心理解
    分割不是“检测更精细”这么简单，它是像素级世界建模，是自动驾驶可行驶区域、医学病灶、机器人操作区域理解的基础。
```

</details>

<details>
<summary><strong>03.1 Basic Definition & Task Variants / 核心定义与任务变体</strong></summary>

图像分割的核心问题是：把图像划分成有意义的区域。

常见类型：

| 类型 | 输出 | 例子 |
|---|---|---|
| Semantic Segmentation / 语义分割 | 每个像素的类别 | 道路、天空、车、人 |
| Instance Segmentation / 实例分割 | 每个对象实例的 mask | 第 1 个人、第 2 个人 |
| Panoptic Segmentation / 全景分割 | thing + stuff 统一 | 人、车、道路、天空全部统一标注 |
| Part Segmentation / 部件分割 | 对象部件 | 人体部件、动物部件、机械零件 |
| Referring Segmentation / 指代表达分割 | 文本指代对象 mask | “左边穿红衣服的人” |
| Interactive Segmentation / 交互分割 | 点击/框提示下的 mask | 用户点一下，模型分出对象 |
| Video Object Segmentation / 视频目标分割 | 跨帧对象 mask | 第 1 帧选中目标，后续持续分割 |

检测和分割的关系：

```text
Detection：给出对象的粗略位置 box
Segmentation：给出对象或区域的精确像素 mask
```

#### Task Variants / 任务变体

```text
Semantic Segmentation / 语义分割
Instance Segmentation / 实例分割
Panoptic Segmentation / 全景分割
Part Segmentation / 部件分割
Amodal Segmentation / 非模态分割
Camouflaged Object Segmentation / 伪装目标分割
Salient Object Segmentation / 显著目标分割
Transparent Object Segmentation / 透明物体分割
Medical Image Segmentation / 医学图像分割
Remote Sensing Segmentation / 遥感分割
Video Object Segmentation / 视频目标分割
Referring Image Segmentation / 指代表达图像分割
Interactive Segmentation / 交互式分割
Open-vocabulary Segmentation / 开放词汇分割
```

新手要注意：

```text
医学分割、遥感分割、伪装分割、透明物体分割，不一定是新范式；
它们通常是“同一分割框架在特殊数据、特殊对象、特殊难点上的应用与改造”。
```

</details>

<details>
<summary><strong>03.2 Method Evolution / 方法演化主线</strong></summary>

<details open>
<summary><strong>03.2.1 FCN and Encoder-Decoder / FCN 与编码器-解码器</strong></summary>

FCN 的关键思想是：把分类网络中的全连接层替换成卷积层，使网络可以输出空间尺寸的预测图。

```text
Classification network → Fully Convolutional Network → Pixel prediction
```

U-Net 则把 encoder-decoder 和 skip connection 做得非常经典，尤其适合医学影像等数据较少的场景。它的结构思想很直观：

```text
Encoder：逐步压缩图像，提取高层语义
Decoder：逐步恢复分辨率，输出像素预测
Skip connection：把低层细节传给解码器，保留边界信息
```

新手应该注意：U-Net 不只是医学分割模型，而是一种非常通用的 dense prediction 结构思想，后续许多低层视觉、生成、遥感、医学模型都在使用类似 U 型结构。

</details>

<details>
<summary><strong>03.2.2 Context Modeling / 上下文建模：DeepLab、PSPNet、HRNet</strong></summary>

语义分割的一个难点是：像素级预测既需要局部边界细节，也需要全局语义上下文。

DeepLab 系列使用 atrous / dilated convolution 扩大感受野，并引入 ASPP 进行多尺度上下文建模。PSPNet 使用 pyramid pooling 聚合不同尺度上下文。HRNet 则保持高分辨率分支并进行多尺度特征交换，适合精细空间定位。

可以这样理解：

```text
FCN：让网络能输出像素级结果
U-Net：强调编码器-解码器和细节恢复
DeepLab / PSPNet：强调多尺度上下文
HRNet：强调高分辨率特征持续保留
```

</details>

<details>
<summary><strong>03.2.3 Transformer Segmentation / Transformer 分割</strong></summary>

Transformer 进入分割后，主要解决长程依赖和全局上下文建模问题。

```text
SETR：把语义分割看成序列到序列预测
SegFormer：层次化 Transformer encoder + 轻量 MLP decoder
```

SegFormer 很适合新手理解 Transformer segmentation，因为它不是简单堆复杂 decoder，而是强调：

```text
好的多尺度 encoder + 简洁 decoder，也可以做强分割
```

它还避免了固定 positional encoding 在分辨率变化时的问题，因此在泛化和效率上有优势。

</details>

<details>
<summary><strong>03.2.4 Universal Segmentation / 统一分割：MaskFormer、Mask2Former、OneFormer</strong></summary>

传统分割把语义分割、实例分割、全景分割当成不同任务，分别设计模型。统一分割的目标是：

```text
把分割统一成 mask classification 问题。
```

MaskFormer 的思想是：模型预测一组 mask，每个 mask 再分类。Mask2Former 在此基础上使用 masked attention，进一步统一 semantic、instance、panoptic 三类分割任务。OneFormer 更进一步，通过任务条件 token 和联合训练，让单个模型在训练一次后支持多种分割任务。

这条线对新手很重要，因为它说明分割的研究重心从“为每个任务设计专门 head”，转向了“统一输出格式和统一模型接口”。

</details>

<details>
<summary><strong>03.2.5 Promptable Segmentation / 可提示分割：SAM 与 SAM 2</strong></summary>

SAM 的核心变化是：分割不再只是“给固定类别做像素分类”，而是变成一个可提示任务。

```text
Prompt / 提示：点、框、mask、文本接口
Output / 输出：对应对象或区域的 mask
```

SAM 的价值在于三点：

```text
1. Promptable：可以通过点击、框等提示控制分割对象
2. Zero-shot transfer：可以迁移到新图像分布和新对象
3. Data engine：通过数据引擎构建大规模 mask 数据集
```

SAM 2 把可提示分割从图像扩展到视频，使用 streaming memory 处理实时视频，并让图像分割与视频分割在同一个框架中统一。对自动驾驶、机器人、视频编辑、数据标注来说，这非常关键。

</details>

<details>
<summary><strong>03.2.6 Open-vocabulary and Referring Segmentation / 开放词汇与指代表达分割</strong></summary>

开放词汇分割关心：模型能否分割训练时没有显式标注过的类别。

指代表达分割关心：模型能否根据自然语言描述分割目标。

```text
Open-vocabulary Segmentation："segment all fire hydrants"
Referring Segmentation："segment the man on the left wearing a red shirt"
```

这类任务连接了分割、多模态理解和语言引导感知。Grounded-SAM 这类组合系统常见流程是：

```text
文本提示 → Grounding DINO 找框 → SAM 生成 mask
```

这说明现代视觉系统越来越像“模块组合”：检测器负责语言定位，分割基础模型负责精细 mask。

</details>

</details>

<details>
<summary><strong>03.3 Upstream & Downstream / 上下游定位</strong></summary>

图像分割把对象和场景从框级定位推进到像素级区域，是许多系统的空间精细化接口。

```text
上游输入：图像、视频帧、文本/点/框提示、检测框、基础模型特征
本章输出：semantic mask、instance mask、panoptic map、promptable mask、video mask
下游模块：自动驾驶可行驶区域、医学病灶分析、遥感地物制图、机器人抓取区域、视频编辑与数据标注
系统价值：把“在哪里”细化为“精确轮廓是什么”
```

</details>

<details>
<summary><strong>03.4 Representative Works / 代表性工作速览</strong></summary>

| 年份 / Year | 方法 / Work | 位置 / Position | 为什么重要 / Why it matters |
|---:|---|---|---|
| 2015 | FCN | 语义分割起点 | 把分类 CNN 改成全卷积网络，输出像素级预测 |
| 2015 | U-Net | 医学分割与 U 型结构 | Encoder-decoder + skip connection 的经典结构 |
| 2015-2018 | DeepLab 系列 | 多尺度上下文 | Atrous convolution / ASPP，扩大感受野 |
| 2017 | PSPNet | 金字塔上下文 | Pyramid pooling 聚合全局上下文 |
| 2019 | HRNet | 高分辨率表示 | 持续保持高分辨率特征，适合精细定位 |
| 2021 | SegFormer | Transformer 分割 | 层次化 Transformer encoder + 轻量 MLP decoder |
| 2021/2022 | MaskFormer | mask classification | 把分割表述为 mask 分类问题 |
| 2022 | Mask2Former | 通用分割 | 同一架构处理 semantic / instance / panoptic segmentation |
| 2022 | OneFormer | 一次训练多任务分割 | 使用 task token 和联合训练统一多种分割任务 |
| 2023 | SAM | 可提示分割基础模型 | 点/框/mask 提示，SA-1B 数据，zero-shot transfer |
| 2024 | SAM 2 | 图像与视频统一分割 | 用 streaming memory 支持实时视频可提示分割 |
| 2022-2024 | X-Decoder / SEEM / Grounded-SAM | 开放词汇与多模态分割 | 把语言、检测、分割组合为开放世界感知系统 |

</details>

<details>
<summary><strong>03.5 Paper Positioning / 论文归位指引</strong></summary>

读分割论文时，先判断它是哪种分割：

```text
Semantic / Instance / Panoptic / Part / Referring / Interactive / Video / Open-vocabulary
```

然后判断它改的是哪一层：

```text
1. Encoder：CNN、Transformer、Mamba、foundation feature？
2. Decoder：U-Net decoder、MLP decoder、mask decoder、prompt decoder？
3. Output：pixel label、mask set、panoptic map、text-conditioned mask？
4. Training：全监督、弱监督、半监督、自监督、promptable、foundation pretraining？
5. Domain：自然图像、医学、遥感、自动驾驶、工业、机器人？
```

例子：

```text
Paper: SAM 2
主任务：Promptable Segmentation / 可提示分割
交叉任务：Video Object Segmentation / 视频目标分割
核心变化：从图像可提示分割扩展到图像+视频统一分割
系统价值：交互标注、视频编辑、机器人场景对象持续分割
```

```text
Paper: SegFormer
主任务：Semantic Segmentation / 语义分割
方法主线：Transformer Segmentation
核心变化：层次化 Transformer encoder + 简洁 MLP decoder
适合归位：Transformer backbone 在密集预测中的实用化路线
```

</details>

<details>
<summary><strong>03.6 Paper Cards / 核心论文卡片</strong></summary>

> 本节集中放置本章代表论文入口。正文和代表论文表格中的方法名优先跳转到这里，外部 Paper / Code / Project 链接只在论文卡片中出现。

<a id="paper-03-fcn"></a>

#### FCN

- **Title / 标题**：FCN
- **Year / 年份**：2015
- **Core Contribution / 核心贡献**：将分类 CNN 改造为全卷积网络，使端到端像素级预测成为可能。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1411.4038)
<a id="paper-03-u-net"></a>

#### U-Net

- **Title / 标题**：U-Net
- **Year / 年份**：2015
- **Core Contribution / 核心贡献**：用 U 形编码器—解码器和跳连恢复细节，成为医学与密集预测任务的基础结构。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1505.04597)
<a id="paper-03-deeplabv3"></a>

#### DeepLabv3+

- **Title / 标题**：DeepLabv3+
- **Year / 年份**：2018
- **Core Contribution / 核心贡献**：用空洞卷积与 ASPP 建模多尺度上下文，提高语义分割的空间感知能力。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1802.02611)
<a id="paper-03-pspnet"></a>

#### PSPNet

- **Title / 标题**：PSPNet
- **Year / 年份**：2017
- **Core Contribution / 核心贡献**：通过金字塔池化聚合全局与局部上下文，增强场景级语义分割。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1612.01105)
<a id="paper-03-hrnet"></a>

#### HRNet

- **Title / 标题**：HRNet
- **Year / 年份**：2019
- **Core Contribution / 核心贡献**：保持高分辨率分支并持续交换多尺度特征，提升精细定位能力。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1904.04514)
<a id="paper-03-segformer"></a>

#### SegFormer

- **Title / 标题**：SegFormer
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：用层次化 Transformer encoder 与轻量 MLP decoder 实现简洁高效的语义分割。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2105.15203)
<a id="paper-03-maskformer"></a>

#### MaskFormer

- **Title / 标题**：MaskFormer
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：将分割统一为 mask classification，弱化不同分割任务的 head 差异。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2107.06278)
<a id="paper-03-mask2former"></a>

#### Mask2Former

- **Title / 标题**：Mask2Former
- **Year / 年份**：2021/2022
- **Core Contribution / 核心贡献**：用 masked attention 统一 semantic、instance 与 panoptic segmentation。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2112.01527)
<a id="paper-03-oneformer"></a>

#### OneFormer

- **Title / 标题**：OneFormer
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：通过任务条件输入实现一次训练支持多类分割任务。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2211.06220)
<a id="paper-03-sam"></a>

#### SAM

- **Title / 标题**：SAM
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：将分割定义为可提示接口，并用大规模数据引擎支撑零样本迁移。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2304.02643)
<a id="paper-03-sam-2"></a>

#### SAM 2

- **Title / 标题**：SAM 2
- **Year / 年份**：2024
- **Core Contribution / 核心贡献**：把可提示分割扩展到图像和视频统一框架，引入流式记忆处理时序对象。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2408.00714)
</details>

### 04. Object Tracking & Video Understanding / 目标跟踪与视频理解

<details open>
<summary><strong>04.0 Quick Overview / 一页速览</strong></summary>

```text
Object Tracking & Video Understanding / 目标跟踪与视频理解

├── 任务本质：从单帧理解走向时序世界理解
├── 输入：视频帧序列 / 检测结果 / 初始目标框 / 文本指令 / 多模态视频
├── 输出：目标轨迹、跨帧 ID、动作类别、事件边界、视频语义回答
│
├── Tracking / 目标跟踪
│   ├── SOT：给定第一帧目标，后续持续定位
│   ├── MOT：检测多个目标，并保持跨帧 ID
│   ├── VOS：视频中持续输出目标 mask
│   └── MOTS：多目标跟踪 + 分割
│
├── Video Understanding / 视频理解
│   ├── Action Recognition / 动作识别
│   ├── Temporal Action Localization / 时序动作定位
│   ├── Video Captioning / 视频描述
│   ├── Video QA / 视频问答
│   ├── Long-video Understanding / 长视频理解
│   └── Video LLM / 视频大模型
│
└── 新手核心理解
    检测回答“这一帧有什么”，跟踪回答“它是不是同一个对象”，视频理解回答“这段时间发生了什么”。
```

</details>

<details>
<summary><strong>04.1 Basic Definition & Task Variants / 核心定义与任务变体</strong></summary>

单帧视觉只能看到某一时刻；视频视觉要理解时间。

#### Tracking / 跟踪

```text
输入：视频 + 目标初始框 / 或每帧检测结果
输出：目标在每一帧的位置、ID、轨迹，有时还包括 mask
```

#### Video Understanding / 视频理解

```text
输入：视频片段或长视频
输出：动作类别、事件时间段、视频描述、问答、推理结果
```

它们和检测的关系：

```text
检测：每一帧独立找目标
跟踪：把跨帧目标连起来
视频理解：理解目标、动作、场景、事件之间的时序关系
```

#### Task Variants / 任务变体

```text
Single Object Tracking, SOT / 单目标跟踪
Multiple Object Tracking, MOT / 多目标跟踪
3D Multi-object Tracking / 三维多目标跟踪
Multi-object Tracking and Segmentation, MOTS / 多目标跟踪与分割
Video Object Segmentation, VOS / 视频目标分割
Action Recognition / 动作识别
Activity Recognition / 活动识别
Temporal Action Localization / 时序动作定位
Video Captioning / 视频描述
Video Question Answering / 视频问答
Video Grounding / 视频定位
Long-video Understanding / 长视频理解
Egocentric Video Understanding / 第一视角视频理解
Anomaly Event Detection / 异常事件检测
Accident Anticipation / 事故预判
```

</details>

<details>
<summary><strong>04.2 Method Evolution / 方法演化主线</strong></summary>

#### Object Tracking / 目标跟踪方法主线

<details open>
<summary><strong>04.2.1 Single Object Tracking, SOT / 单目标跟踪</strong></summary>

SOT 的设定通常是：第一帧给定一个目标框，模型需要在后续帧持续找到同一目标。

传统方法如 KCF 使用相关滤波，强调速度。深度学习后，Siamese 系列成为重要主线：

```text
SiamFC：把跟踪变成模板图和搜索图的相似性匹配
SiamRPN：把 RPN 引入 Siamese 跟踪，实现分类 + 回归
SiamRPN++：改进深层 backbone 和特征聚合
```

Transformer 跟踪器进一步把模板和搜索区域的关系建模交给注意力机制：

```text
STARK：用 encoder-decoder Transformer 直接预测目标框
OSTrack：one-stream 框架，统一特征学习与关系建模
MixFormer：混合注意力，把目标模板和搜索区域更深融合
```

新手可以这样理解：

```text
Siamese tracking：匹配“这个目标长什么样”
Transformer tracking：建模“目标模板和当前搜索区域之间的关系”
```

</details>

<details>
<summary><strong>04.2.2 Multiple Object Tracking, MOT / 多目标跟踪</strong></summary>

MOT 的目标是：视频里有多个目标，需要每帧检测并保持 ID 一致。

经典流程是 tracking-by-detection：

```text
每帧目标检测 → 跨帧关联 → 轨迹管理
```

代表方法：

```text
SORT：Kalman Filter + Hungarian matching
DeepSORT：加入 ReID 外观特征
ByteTrack：利用低分检测框，改进遮挡和低置信目标关联
OC-SORT：强调观测中心的关联和运动建模
BoT-SORT：融合更强 ReID、运动补偿等工程改进
```

MOT 里最核心的问题不是“检测准不准”这么简单，而是：

```text
遮挡后 ID 会不会丢？
两个相似目标交叉后会不会换 ID？
低置信检测结果要丢弃还是利用？
运动模型和外观特征如何平衡？
```

</details>

<details>
<summary><strong>04.2.3 Video Object Segmentation, VOS / 视频目标分割</strong></summary>

VOS 是跟踪和分割的结合：不是只跟踪框，而是持续输出目标 mask。

```text
第一帧给目标 mask → 后续帧持续分割同一目标
```

典型方向：

```text
Mask propagation：把上一帧 mask 传播到下一帧
Memory-based VOS：用历史帧记忆帮助当前分割
Transformer / Attention VOS：跨帧关系建模
Promptable Video Segmentation：SAM 2 把点/框提示扩展到视频
```

VOS 对机器人和视频编辑很重要，因为很多任务需要“持续知道这个对象的精确轮廓”。

</details>

#### 04.2.4 Video Understanding / 视频理解方法主线

<details open>
<summary><strong>04.2.4.1 From Two-stream to 3D CNN / 从双流网络到 3D CNN</strong></summary>

早期动作识别常用双流网络：

```text
RGB stream：看外观
Optical flow stream：看运动
```

C3D 和 I3D 把 2D 卷积扩展到 3D，让网络直接学习时空特征。I3D 的关键是把成熟的 2D 图像分类网络“膨胀”为 3D 网络，并借助 Kinetics 这样更大规模的视频动作数据集训练。

</details>

<details>
<summary><strong>04.2.4.2 SlowFast and Temporal Modeling / SlowFast 与时序建模</strong></summary>

SlowFast 的思想非常直观：视频理解既需要慢速观察语义，也需要快速捕捉运动。

```text
Slow pathway：低帧率，高通道，捕捉空间语义
Fast pathway：高帧率，低通道，捕捉细粒度运动
```

这说明视频模型不能只把视频当成“很多张图片”，而要专门考虑不同时间尺度的信息。

</details>

<details>
<summary><strong>04.2.4.3 Video Transformer / 视频 Transformer</strong></summary>

Transformer 进入视频后，一个关键问题是：视频 token 太多，直接全局注意力非常昂贵。

代表路线：

```text
TimeSformer：研究时空注意力如何组织，提出 divided attention 等设计
Video Swin Transformer：把窗口注意力扩展到时空，利用局部性提升效率
MViT / ViViT：多尺度或不同 token 化的视频 Transformer 路线
```

新手可以这样理解：

```text
图像 Transformer 解决空间关系
视频 Transformer 要同时解决空间关系 + 时间关系 + 计算成本
```

</details>

<details>
<summary><strong>04.2.4.4 Self-supervised Video Pretraining / 自监督视频预训练</strong></summary>

视频标注比图像更贵，因此自监督视频预训练非常重要。

VideoMAE 把 MAE 的掩码重建思想推广到视频，通过高比例 tube masking 让模型学习时空表征。它体现了一个趋势：

```text
视频模型不一定只靠动作标签训练，也可以通过遮挡重建学习通用时空特征。
```

</details>

<details>
<summary><strong>04.2.4.5 Video Foundation Models & Video LLM / 视频基础模型与视频大模型</strong></summary>

视频基础模型试图把视频识别、视频文本检索、视频问答、长视频理解等任务统一起来。

代表路线：

```text
InternVideo / InternVideo2：视频基础模型，整合 masked video modeling、图文对比学习、next-token prediction 等训练目标
Video-LLM：把视频编码器接入 LLM，让模型进行视频问答、时序推理、事件理解
Long-video understanding：从短 clip 识别走向长程事件、因果、情节理解
```

这条线对自动驾驶和具身智能非常重要，因为真实世界不是静态图像，而是持续变化的时序过程。

</details>

</details>

<details>
<summary><strong>04.3 Upstream & Downstream / 上下游定位</strong></summary>

跟踪与视频理解把静态感知结果扩展到时间维度。

```text
上游输入：视频帧、检测框、分割 mask、视觉特征、光流或历史记忆
本章输出：跨帧 ID、目标轨迹、视频对象 mask、动作类别、事件/时序表征
下游模块：自动驾驶轨迹预测、行为分析、视频检索、机器人持续操作、安防监控、长视频问答
系统价值：从“单帧看见什么”推进到“同一对象如何变化、事件如何发生”
```

</details>

<details>
<summary><strong>04.4 Representative Works / 代表性工作速览</strong></summary>

| 年份 / Year | 方法 / Work | 位置 / Position | 为什么重要 / Why it matters |
|---:|---|---|---|
| 2010 | TLD | 传统跟踪 | Tracking-Learning-Detection 思路，早期经典跟踪框架 |
| 2014 | KCF | 相关滤波跟踪 | 高速传统跟踪代表 |
| 2016 | SiamFC | Siamese SOT | 用模板-搜索匹配做实时单目标跟踪 |
| 2018 | SiamRPN | Siamese + RPN | 同时做目标分类与框回归，提升跟踪精度 |
| 2019 | SiamRPN++ | 深层 Siamese 跟踪 | 解决深层网络在 Siamese 跟踪中的使用问题 |
| 2021 | STARK | Transformer tracking | 把跟踪转成端到端 box prediction |
| 2022 | OSTrack | One-stream tracking | 统一模板和搜索区域的特征学习与关系建模 |
| 2016 | SORT | MOT tracking-by-detection | Kalman filter + Hungarian matching 的简洁基线 |
| 2017 | DeepSORT | MOT + ReID | 加入外观特征改善 ID 保持 |
| 2021 | ByteTrack | MOT 数据关联 | 利用低分检测框进行更稳健关联 |
| 2022 | OC-SORT / BoT-SORT | MOT 工程改进 | 运动建模、ReID、相机运动补偿等增强 |
| 2017 | I3D | 视频动作识别 | 把 2D ConvNet 膨胀为 3D ConvNet，借助 Kinetics 训练 |
| 2019 | SlowFast | 多时间尺度视频识别 | Slow 路径看语义，Fast 路径看运动 |
| 2021 | TimeSformer | 视频 Transformer | 用时空注意力处理视频分类 |
| 2021/2022 | Video Swin Transformer | 局部视频 Transformer | 把 Swin 的窗口注意力扩展到视频 |
| 2022 | VideoMAE | 自监督视频预训练 | 高比例 tube masking，学习视频时空表征 |
| 2024 | InternVideo2 | 视频基础模型 | 统一视频识别、图文任务、视频对话等多种能力 |
| 2024 | SAM 2 | 视频可提示分割 | 图像与视频统一的 promptable segmentation |

</details>

<details>
<summary><strong>04.5 Paper Positioning / 论文归位指引</strong></summary>

读跟踪论文时，先判断：

```text
1. 是 SOT、MOT、VOS、MOTS，还是 3D tracking？
2. 输入依赖检测器吗？还是第一帧给定目标？
3. 输出是 box、mask、trajectory，还是 ID？
4. 解决的是遮挡、相似目标、长时跟踪、实时性，还是跨域泛化？
```

读视频理解论文时，先判断：

```text
1. 任务是动作分类、时序定位、视频问答、视频描述，还是长视频推理？
2. 模型是 3D CNN、Video Transformer、自监督预训练，还是 Video-LLM？
3. 输入长度是短 clip、长视频，还是第一视角持续视频？
4. 下游服务于监控、自动驾驶、机器人、体育分析、医学视频，还是内容理解？
```

例子：

```text
Paper: OSTrack
主任务：Single Object Tracking / 单目标跟踪
方法主线：Transformer tracking → One-stream tracking
核心变化：模板与搜索区域不再分开提特征再匹配，而是在一个流中联合建模
```

```text
Paper: VideoMAE
主任务：Video Representation Learning / 视频表征学习
方法主线：Self-supervised video pretraining
核心变化：通过高比例视频 tube masking 学习时空表征
```

```text
Paper: InternVideo2
主任务：Video Foundation Model / 视频基础模型
交叉任务：视频识别、视频文本检索、视频问答、视频对话
核心变化：把多种预训练目标和大规模视频数据结合，获得通用视频表征
```

</details>

<details>
<summary><strong>04.6 Paper Cards / 核心论文卡片</strong></summary>

> 本节集中放置本章代表论文入口。正文和代表论文表格中的方法名优先跳转到这里，外部 Paper / Code / Project 链接只在论文卡片中出现。

<a id="paper-04-siamfc"></a>

#### SiamFC

- **Title / 标题**：SiamFC
- **Year / 年份**：2016
- **Core Contribution / 核心贡献**：用 Siamese matching 将跟踪转化为模板与搜索区域的相似性匹配。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1606.09549)
<a id="paper-04-siamrpn"></a>

#### SiamRPN

- **Title / 标题**：SiamRPN
- **Year / 年份**：2018
- **Core Contribution / 核心贡献**：将 RPN 引入 Siamese 跟踪，同时预测目标分类与边界框。
- **Links / 链接**：[Paper](https://openaccess.thecvf.com/content_cvpr_2018/html/Li_High_Performance_Visual_CVPR_2018_paper.html)
<a id="paper-04-siamrpn-plus-plus"></a>

#### SiamRPN++

- **Title / 标题**：SiamRPN++
- **Year / 年份**：2018/2019
- **Core Contribution / 核心贡献**：将 RPN 引入 Siamese 跟踪，同时预测目标分类与边界框。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1812.11703)
<a id="paper-04-stark"></a>

#### STARK

- **Title / 标题**：STARK
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：用 Transformer 进行模板—搜索区域建模，推动跟踪进入 query-based 表征路线。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2103.17154)
<a id="paper-04-ostrack"></a>

#### OSTrack

- **Title / 标题**：OSTrack
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：用 one-stream 架构统一模板和搜索区域建模，简化 Transformer 跟踪流程。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2203.11991)
<a id="paper-04-i3d"></a>

#### I3D

- **Title / 标题**：I3D
- **Year / 年份**：2017
- **Core Contribution / 核心贡献**：将二维卷积膨胀为三维卷积，迁移图像预训练到视频动作识别。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1705.07750)
<a id="paper-04-slowfast"></a>

#### SlowFast

- **Title / 标题**：SlowFast
- **Year / 年份**：2019
- **Core Contribution / 核心贡献**：用慢速语义通道与快速运动通道联合建模视频时序信息。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1812.03982)
<a id="paper-04-timesformer"></a>

#### TimeSformer

- **Title / 标题**：TimeSformer
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：将 Transformer 注意力分解到时间和空间维度，用于视频理解。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2102.05095)
<a id="paper-04-video-swin-transformer"></a>

#### Video Swin Transformer

- **Title / 标题**：Video Swin Transformer
- **Year / 年份**：2021/2022
- **Core Contribution / 核心贡献**：将 Swin 的局部窗口注意力扩展到时空维度，提升视频建模效率。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2106.13230)
<a id="paper-04-videomae"></a>

#### VideoMAE

- **Title / 标题**：VideoMAE
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：用视频 masked modeling 进行自监督预训练，降低视频表示对标注的依赖。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2203.12602)
<a id="paper-04-internvideo2"></a>

#### InternVideo2

- **Title / 标题**：InternVideo2
- **Year / 年份**：2024
- **Core Contribution / 核心贡献**：通过大规模多源视频预训练构建通用视频基础表征。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2403.15377)
</details>

## Part II. Low-level, Generation & Spatial Intelligence / 低层、生成与空间智能

---

### 05. Image Restoration & Enhancement / 图像恢复与增强

<details open>
<summary><strong>05.0 Quick Overview / 一页速览</strong></summary>

#### 05.0 一句话定位 / One-sentence Positioning

**图像恢复、增强与超分**解决的是：当原始图像因为噪声、模糊、雨雾、低光、压缩、低分辨率等问题变得“不好看、不清楚、不适合下游识别”时，如何把它变成更清晰、更稳定、更有用的图像。

它处在视觉系统的最前端：

```text
低质量输入图像
→ 图像恢复 / 增强 / 超分
→ 检测 / 分割 / 跟踪 / OCR / 三维重建 / 多模态理解
```

新手要注意：低层视觉不是“把图修漂亮”这么简单。很多时候，它的真正价值是让后面的检测、分割、识别、导航、三维重建更可靠。

---

</details>

<details>
<summary><strong>05.1 Basic Definition & Task Variants / 核心定义与任务变体</strong></summary>

#### 05.1.1 主要任务 / Main Tasks

```text
Image Restoration / 图像恢复
├── Denoising / 去噪
├── Deblurring / 去模糊
├── Deraining / 去雨
├── Dehazing / 去雾
├── Desnowing / 去雪
├── JPEG Artifact Removal / 压缩伪影去除
├── Inpainting / 图像修复
└── Low-light Enhancement / 低光增强

Image Super-Resolution / 图像超分辨率
├── Classical SR / 合成退化超分
├── Real-world SR / 真实退化超分
├── Blind SR / 未知退化超分
├── Face SR / 人脸超分
├── Video SR / 视频超分
└── Task-driven SR / 面向下游任务的超分

Image Enhancement / 图像增强
├── Contrast Enhancement / 对比度增强
├── Color Correction / 色彩校正
├── HDR Reconstruction / 高动态范围重建
├── Exposure Correction / 曝光校正
└── Nighttime / Adverse Weather Enhancement / 夜间与恶劣天气增强
```

#### 05.1.2 输入与输出 / Input and Output

| 任务 / Task | 输入 / Input | 输出 / Output | 典型用途 / Usage |
|---:|---|---|---|
| 去噪 / Denoising | 有噪图像 | 干净图像 | 医学、手机摄影、监控 |
| 去模糊 / Deblurring | 运动模糊 / 失焦图像 | 清晰图像 | 自动驾驶、手持摄影 |
| 去雨 / 去雾 / 去雪 | 恶劣天气图像 | 可见度更高图像 | 自动驾驶、安防 |
| 超分 / SR | 低分辨率图像 | 高分辨率图像 | 遥感、医学、监控 |
| 低光增强 | 暗光图像 | 明亮且细节保留图像 | 夜间感知、机器人 |

#### 05.1.3 Common Misunderstandings / 常见误区

1. **误区：图像恢复就是让图更好看。**  
   更准确地说，图像恢复要服务于人类视觉或机器视觉。对自动驾驶和医学来说，“好看”不等于“可信”。

2. **误区：PSNR 越高，方法越好。**  
   PSNR 高通常意味着像素接近 GT，但不一定视觉自然；GAN / Diffusion 方法视觉效果好，但可能牺牲真实性。

3. **误区：Diffusion 一定比 CNN / Transformer 好。**  
   Diffusion 在真实退化和感知质量上强，但速度慢、成本高、可能幻觉。工程场景仍大量需要高效 CNN/Transformer。

4. **误区：低层视觉和高层视觉无关。**  
   事实上，低层视觉经常直接影响检测、分割、跟踪、OCR 和三维重建的表现。

</details>

<details>
<summary><strong>05.2 Method Evolution / 方法演化主线</strong></summary>

#### 05.2.1 传统图像处理阶段 / Traditional Image Processing

早期低层视觉主要依赖手工先验：

```text
滤波 / Filtering
→ 稀疏表示 / Sparse Representation
→ 总变分 / Total Variation
→ 非局部相似性 / Non-local Similarity
→ 字典学习 / Dictionary Learning
```

这些方法的核心思想是：图像中存在某种“天然规律”，比如平滑区域应该平滑，边缘应该保持，重复纹理可以互相借用。

优点是可解释，缺点是很难覆盖复杂真实退化。

---

#### 05.2.2 CNN 时代：从手工先验到数据驱动 / CNN Era

CNN 让低层视觉从“设计公式”进入“学习映射”阶段。

典型主线：

```text
SRCNN
→ VDSR / DnCNN
→ EDSR / RCAN
→ SRGAN / ESRGAN
→ MPRNet / Real-ESRGAN
```

这里有两条重要路线：

第一条是 **保真路线 / Fidelity-oriented**：追求 PSNR、SSIM 等指标，输出尽量接近真实高清图。  
第二条是 **感知质量路线 / Perceptual-oriented**：追求视觉真实感，常用 GAN 和 perceptual loss，但可能产生“看起来真实但不一定真实”的细节。

例如 ESRGAN 不是简单“把图变清晰”，而是围绕 SRGAN 的三个关键部件进行改进：网络结构、对抗损失和感知损失，并引入 RRDB 等设计，用于生成更自然的纹理。

---

#### 05.2.3 多阶段恢复：把难问题拆成多步 / Multi-stage Restoration

真实图像退化通常不是单一因素，可能同时有模糊、噪声、低光和压缩伪影。MPRNet 的代表性意义在于，它把图像恢复拆成多个阶段逐步处理，每个阶段既保留局部细节，又吸收上下文信息。

可以这样理解：

```text
一次性恢复：低质量图像 → 高质量图像

多阶段恢复：
低质量图像
→ 初步恢复
→ 细节修正
→ 高分辨率重建
→ 输出
```

MPRNet 的意义不是“用了更深网络”，而是提出一种 progressive restoration 的思路：先解决大问题，再逐步补细节。

---

#### 05.2.4 Transformer 时代：长程依赖与高分辨率效率 / Transformer Era

低层视觉很依赖局部纹理，但也需要长程关系。例如去雨时，要判断一条亮线是雨丝还是图像结构；去模糊时，要判断全局运动方向；超分时，要借助远处相似纹理。

Transformer 被引入后，关键问题变成：

```text
如何建模全局关系，同时不让高分辨率图像的计算爆炸？
```

代表路线：

```text
SwinIR
→ Uformer
→ Restormer
→ HAT
```

SwinIR 的重要性在于，它把 Swin Transformer 作为图像恢复的强基线，覆盖超分、去噪和 JPEG 伪影去除等任务。Restormer 则强调高分辨率图像恢复中的高效 Transformer 设计，用 transposed attention 等方式减少高分辨率注意力的负担。

---

#### 05.2.5 简化与高效路线：不是越复杂越好 / Efficient Restoration

NAFNet 是一个很适合新人理解的节点。它的启发是：很多 SOTA 恢复网络越来越复杂，但有些激活函数和复杂模块并非必要。NAFNet 去掉常见非线性激活，用更简洁的结构取得强效果。

这说明低层视觉有一条很重要的路线：

```text
不是盲目堆 Transformer / Diffusion
而是重新审视：
哪些模块真的必要？
哪些计算可以省？
哪些设计只是工程惯性？
```

---

#### 05.2.6 Diffusion 时代：从确定性恢复到生成式恢复 / Diffusion Era

扩散模型进入低层视觉后，恢复任务的思路发生变化：

```text
传统恢复：给定低质量图像，预测一个确定的高清结果
生成式恢复：给定低质量图像，生成一个合理且自然的高清结果
```

这对真实退化超分、老照片修复、严重模糊恢复很有吸引力，因为这些任务本身就有多种可能答案。

但风险也很明显：扩散模型可能“幻觉”出不存在的细节。对于医学、遥感、自动驾驶等高风险场景，生成式恢复必须谨慎使用。

</details>

<details>
<summary><strong>05.3 Upstream & Downstream / 上下游定位</strong></summary>

图像恢复与增强通常位于视觉系统前端，是输入质量控制和鲁棒性感知的重要环节。

```text
上游输入：低光、噪声、模糊、雨雾雪、压缩伪影、低分辨率或受损图像
本章输出：去噪 / 去模糊 / 去雨雾 / 超分 / 增强后的图像或特征
下游模块：检测、分割、跟踪、OCR、三维重建、医学诊断、遥感解译、夜间自动驾驶感知
核心风险：增强结果可能改变证据或生成幻觉，因此高风险场景要关注真实性和下游一致性
```

判断一篇恢复论文的系统价值时，不只看视觉效果，还要看它是否提升下游任务、是否保留可验证细节、是否满足实时或端侧部署约束。

</details>

<details>
<summary><strong>05.4 Representative Works / 代表性工作速览</strong></summary>

| 年份 / Year | 方法 / Work | 位置 / Position | 为什么重要 / Why it matters |
|---:|---|---|---|
| 2014 | SRCNN | CNN 超分起点 | 将单图像超分表述为端到端 CNN 映射 |
| 2017 | SRGAN | 感知超分 | 引入 GAN，让超分从高 PSNR 走向视觉真实感 |
| 2018 | ESRGAN | 高质量感知超分 | 改进 SRGAN 的结构、对抗损失和感知损失 |
| 2021 | MPRNet | 多阶段恢复 | 将去雨、去模糊、去噪等恢复任务组织成渐进式恢复 |
| 2021 | SwinIR | Transformer 恢复基线 | 用 Swin Transformer 统一超分、去噪、压缩伪影去除 |
| 2021 | Real-ESRGAN | 真实世界超分 | 用复杂退化建模模拟真实退化，推动实用超分 |
| 2022 | Restormer | 高分辨率 Transformer 恢复 | 解决高分辨率恢复中全局建模与效率矛盾 |
| 2022 | NAFNet | 简洁高效恢复 | 说明低层视觉不一定要复杂模块堆叠 |
| 2023 | HAT | 混合注意力恢复 | 将通道注意力和窗口注意力结合，提升恢复能力 |
| 2023–2025 | Diffusion Restoration | 生成式恢复 | 将恢复从确定性预测推向条件生成 |

</details>

<details>
<summary><strong>05.5 Paper Positioning / 论文归位指引</strong></summary>

看到一篇图像恢复、增强或超分论文时，不要只问“用了什么网络”，而要按下面四个问题定位：

```text
1. 它处理什么退化？
   噪声 / 模糊 / 雨雾 / 低光 / 压缩 / 低分辨率 / 混合退化

2. 它追求什么目标？
   PSNR 指标 / 感知质量 / 下游任务表现 / 实时部署 / 真实退化泛化

3. 它改的是哪个层面？
   退化建模 / 网络结构 / 损失函数 / 数据生成 / 训练策略 / 采样加速

4. 它适合什么系统？
   手机摄影 / 自动驾驶 / 医学 / 遥感 / 安防 / 机器人
```

例子：

```text
一篇“Diffusion-based Real-world Super-Resolution”论文
主任务：图像超分
方法路线：扩散模型 / 生成式恢复
核心问题：真实退化复杂、多解性强
风险点：可能生成幻觉细节
下游意义：视觉质量提升，但高风险场景需谨慎
```

</details>

<details>
<summary><strong>05.6 Paper Cards / 核心论文卡片</strong></summary>

> 本节集中放置本章代表论文入口。正文和代表论文表格中的方法名优先跳转到这里，外部 Paper / Code / Project 链接只在论文卡片中出现。

<a id="paper-srcnn"></a>

#### SRCNN

- **Title / 标题**：Image Super-Resolution Using Deep Convolutional Networks
- **Year / 年份**：2014/2015
- **Core Contribution / 核心贡献**：首次以端到端 CNN 直接学习低分辨率到高分辨率映射，开启深度超分路线。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1501.00092)
<a id="paper-srgan"></a>

#### SRGAN

- **Title / 标题**：Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network
- **Year / 年份**：2017
- **Core Contribution / 核心贡献**：将对抗学习引入超分辨率，优化感知真实感而不只追求像素误差。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1609.04802)
<a id="paper-esrgan"></a>

#### ESRGAN

- **Title / 标题**：Enhanced Super-Resolution Generative Adversarial Networks
- **Year / 年份**：2018
- **Core Contribution / 核心贡献**：改进 SRGAN 的生成器、判别器和感知损失，提升真实感图像超分质量。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1809.00219)
<a id="paper-mprnet"></a>

#### MPRNet

- **Title / 标题**：Multi-Stage Progressive Image Restoration
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：用多阶段渐进恢复框架处理去雨、去模糊、去噪等复合退化。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2102.02808)
<a id="paper-swinir"></a>

#### SwinIR

- **Title / 标题**：Image Restoration Using Swin Transformer
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：将 Swin Transformer 引入图像恢复，利用窗口注意力建模局部与长程依赖。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2108.10257) / [Code](https://github.com/JingyunLiang/SwinIR)
<a id="paper-real-esrgan"></a>

#### Real-ESRGAN

- **Title / 标题**：Training Real-World Blind Super-Resolution with Pure Synthetic Data
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：通过合成真实退化训练盲超分模型，增强真实场景图像增强能力。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2107.10833) / [Code](https://github.com/xinntao/Real-ESRGAN)
<a id="paper-restormer"></a>

#### Restormer

- **Title / 标题**：Efficient Transformer for High-Resolution Image Restoration
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：用高效 Transformer 结构处理高分辨率图像恢复的计算和全局建模问题。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2111.09881) / [Code](https://github.com/swz30/Restormer)
<a id="paper-nafnet"></a>

#### NAFNet

- **Title / 标题**：Simple Baselines for Image Restoration
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：提出无需复杂非线性激活的简洁恢复基线，证明结构简化也能取得强性能。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2204.04676) / [Code](https://github.com/megvii-research/NAFNet)
<a id="paper-hat"></a>

#### HAT

- **Title / 标题**：Activating More Pixels in Image Super-Resolution Transformer
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：通过混合注意力激活更多像素关系，提升 Transformer 超分模型的细节恢复能力。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2205.04437) / [Code](https://github.com/XPixelGroup/HAT)
</details>

### 06. Image Fusion & Cross-modal Fusion / 图像融合与跨模态融合

<details open>
<summary><strong>06.0 Quick Overview / 一页速览</strong></summary>

#### 06.0 一句话定位 / One-sentence Positioning

**图像融合**解决的是：当一个传感器看不全世界时，如何把多个图像源的信息合成一个更有用的表示。

它不是简单地“把两张图叠加”，而是在回答：

```text
红外看到热目标，可见光看到纹理；
医学 CT 看到骨骼，MRI 看到软组织；
遥感全色图像分辨率高，多光谱图像光谱信息多；
自动驾驶 LiDAR 准确测距，相机语义丰富。
如何融合？
```

---

</details>

<details>
<summary><strong>06.1 Basic Definition & Task Variants / 核心定义与任务变体</strong></summary>

#### Fusion Taxonomy / 融合任务分类

#### 06.1.1 按任务类型划分 / By Fusion Task

```text
Image Fusion / 图像融合
├── Infrared-Visible Fusion / 红外-可见光融合
├── Multi-focus Fusion / 多焦点融合
├── Multi-exposure Fusion / 多曝光融合
├── Medical Image Fusion / 医学图像融合
├── Remote Sensing Fusion / 遥感图像融合
│   ├── Pan-sharpening / 全色锐化
│   ├── Hyperspectral-Multispectral Fusion / 高光谱-多光谱融合
│   └── Spatiotemporal Fusion / 时空融合
├── RGB-D Fusion / RGB-深度融合
├── RGB-T Fusion / RGB-热红外融合
├── Event-RGB Fusion / 事件相机-RGB 融合
└── Task-driven Fusion / 面向下游任务的融合
```

#### 06.1.2 按系统位置划分 / By System Position

```text
Pixel-level Fusion / 像素级融合
    原始图像直接融合，输出一张融合图像

Feature-level Fusion / 特征级融合
    各模态先提特征，再在中间层融合

Decision-level Fusion / 决策级融合
    各模态各自预测，最后合并结果

Task-driven Fusion / 任务驱动融合
    融合结果不只追求视觉质量，还要提升检测、分割、识别等任务
```

</details>

<details>
<summary><strong>06.2 Method Evolution / 方法演化主线</strong></summary>

#### 06.2.1 传统融合：规则与变换域 / Traditional Fusion

早期融合常用：

```text
加权平均
→ 金字塔融合
→ 小波变换
→ 稀疏表示
→ 多尺度分解
```

这些方法通常先把图像拆成不同尺度或频率，再分别融合亮度、纹理、边缘等成分。

优点是可解释，缺点是缺少语义理解，无法知道“哪些信息对下游任务最重要”。

---

#### 06.2.2 深度学习融合：从手工规则到特征学习 / Deep Fusion

DenseFuse 是深度学习红外-可见光融合中的代表性早期工作。它用编码器提取两种图像的特征，再通过融合层和解码器生成融合图像。它的重要性在于：融合规则不再完全手工设计，而是交给网络学习。

典型路线：

```text
DeepFuse / DenseFuse
→ DIDFuse
→ GAN-based Fusion
→ Attention-based Fusion
```

这里的核心变化是：

```text
传统方法：人设计融合规则
深度方法：网络学习融合特征
```

---

#### 06.2.3 Transformer 融合：长程依赖与跨模态关系 / Transformer Fusion

融合任务不只需要局部纹理，也需要全局关系。例如夜间图像中，红外亮目标可能是行人，但可见光纹理很弱；此时模型需要在全局范围内判断哪些信息更可靠。

Transformer 融合路线通常强调：

```text
长程依赖
跨模态注意力
全局结构保持
不同模态之间的信息互补
```

SwinFusion 是比较典型的节点，它把 Swin Transformer 的窗口注意力和跨域长程建模引入通用图像融合。

---

#### 06.2.4 任务驱动融合：融合不是终点 / Task-driven Fusion

这是新手最容易忽略的一点：融合图像本身不是最终目的。

在自动驾驶、安防、机器人、遥感中，融合图像最终要服务于：

```text
检测 / Detection
分割 / Segmentation
跟踪 / Tracking
识别 / Recognition
导航 / Navigation
```

TarDAL 和 SeAFusion 这类工作的重要性就在于，它们不再只看融合图像视觉效果，而把下游检测或分割任务纳入优化目标。

可以这样理解：

```text
传统融合：融合图像看起来更好
任务驱动融合：融合图像让机器看得更准
```

---

#### 06.2.5 语义引导融合：从像素互补到语义互补 / Semantic-guided Fusion

语义引导融合进一步问：

```text
哪些区域是目标？
哪些区域是背景？
哪些纹理对检测重要？
哪些热源是真实对象？
```

这类方法会引入语义分割、目标检测、视觉语言模型或文本提示，让融合过程知道“什么信息更重要”。

这也是图像融合与多模态大模型相交的地方。未来图像融合可能不只是红外+可见光，而是：

```text
红外图像 + 可见光图像 + 语义标签 + 文本提示 + 下游任务反馈
```

</details>

<details>
<summary><strong>06.3 Upstream & Downstream / 上下游定位</strong></summary>

#### Relationship to Detection, Driving and Robotics / 与检测、自动驾驶、机器人关系

#### 06.4.1 与目标检测 / Detection

多模态目标检测本质上是融合问题的下游版本：

```text
RGB-T Detection / RGB-热红外检测
RGB-D Detection / RGB-深度检测
LiDAR-Camera Detection / 激光雷达-相机检测
Radar-Camera Detection / 雷达-相机检测
Hyperspectral Detection / 高光谱检测
Event-based Detection / 事件相机检测
```

这些方向不应该只放在“目标检测”里，也应该出现在“图像融合 / 跨模态融合”里。

---

#### 06.4.2 与自动驾驶 / Autonomous Driving

自动驾驶中的融合有多个层级：

```text
Camera + LiDAR
Camera + Radar
Camera + BEV
Camera + HD Map
Camera + V2X
```

早期常见的是点云投影到图像或图像特征投影到 3D；后来 BEVFusion 等方法强调把多模态统一到 BEV 表征中，让检测、分割、地图构建都在同一空间完成。

---

#### 06.4.3 与具身智能 / Embodied AI

机器人融合不只看图像，还包括：

```text
RGB
Depth
Tactile / 触觉
Force / 力觉
Proprioception / 本体感受
Language / 语言
Action History / 动作历史
```

具身智能里的融合最终要服务于动作，因此它更关注：

```text
这个物体能不能抓？
抓哪里？
推会怎样？
这个语言指令对应哪个空间目标？
```

</details>

<details>
<summary><strong>06.4 Representative Works / 代表性工作速览</strong></summary>

| 年份 / Year | 方法 / Work | 位置 / Position | 为什么重要 / Why it matters |
|---:|---|---|---|
| 传统阶段 | Wavelet / Pyramid Fusion | 变换域融合 | 通过多尺度分解融合纹理与结构 |
| 2018 | DenseFuse | 深度红外-可见光融合 | 用深度编码器和 dense block 学习融合特征 |
| 2020 | DIDFuse | 图像分解融合 | 将图像分解为背景和细节特征进行融合 |
| 2022 | TarDAL | 检测驱动融合 | 把目标检测目标纳入红外-可见光融合 |
| 2022 | SwinFusion | Transformer 通用融合 | 用 Swin Transformer 学习跨域长程依赖 |
| 2022 | SeAFusion | 语义感知融合 | 让语义分割任务反向指导融合 |
| 2024 | Semantic-aware Multi-guided Fusion | 语义与多引导融合 | 进一步强调跨模态关系建模和下游任务提升 |
| 2024–2025 | VLM-guided Fusion | 视觉语言引导融合 | 利用文本语义和视觉语言模型指导融合 |

</details>

<details>
<summary><strong>06.5 Paper Positioning / 论文归位指引</strong></summary>

看到一篇融合论文时，可以用下面模板定位：

```text
1. 融合对象是什么？
   红外-可见光 / 多焦点 / 多曝光 / 医学 / 遥感 / RGB-D / LiDAR-Camera

2. 融合发生在哪一层？
   像素级 / 特征级 / 决策级 / BEV级 / 任务级

3. 优化目标是什么？
   视觉质量 / 信息保真 / 检测性能 / 分割性能 / 实时性 / 鲁棒性

4. 方法核心是什么？
   多尺度分解 / CNN / GAN / Transformer / 语义监督 / VLM 引导

5. 下游任务是什么？
   人看 / 检测 / 分割 / 自动驾驶 / 医学诊断 / 机器人操作
```

例子：

```text
一篇“Semantic-guided Infrared-Visible Fusion for Object Detection”论文
主任务：图像融合
交叉任务：多模态目标检测
方法路线：语义引导 / 任务驱动融合
核心价值：不仅输出融合图像，还提升检测性能
```

</details>

<details>
<summary><strong>06.6 Paper Cards / 核心论文卡片</strong></summary>

> 本节集中放置本章代表论文入口。正文和代表论文表格中的方法名优先跳转到这里，外部 Paper / Code / Project 链接只在论文卡片中出现。

<a id="paper-densefuse"></a>

#### DenseFuse

- **Title / 标题**：DenseFuse: A Fusion Approach to Infrared and Visible Images
- **Year / 年份**：2018
- **Core Contribution / 核心贡献**：用密集连接编码器融合红外与可见光图像，代表早期深度图像融合路线。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1804.08361) / [Code](https://github.com/hli1221/imagefusion_densefuse)
<a id="paper-didfuse"></a>

#### DIDFuse

- **Title / 标题**：DIDFuse: Deep Image Decomposition for Infrared and Visible Image Fusion
- **Year / 年份**：2020
- **Core Contribution / 核心贡献**：用图像分解思想分离结构与细节信息，提升红外—可见光融合的可解释性。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2003.09210) / [Code](https://github.com/Zhaozixiang1228/IVIF-DIDFuse)
<a id="paper-tardal"></a>

#### TarDAL

- **Title / 标题**：Target-Aware Dual Adversarial Learning and a Multi-scenario Multi-modality Benchmark to Fuse Infrared and Visible for Object Detection
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：将目标感知和对抗学习引入融合，使融合结果更服务于下游检测。
- **Links / 链接**：[Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Liu_Target-Aware_Dual_Adversarial_Learning_and_a_Multi-Scenario_Multi-Modality_Benchmark_To_CVPR_2022_paper.html)
<a id="paper-swinfusion"></a>

#### SwinFusion

- **Title / 标题**：SwinFusion: Cross-domain Long-range Learning for General Image Fusion via Swin Transformer
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：用 Swin Transformer 建模跨域长程依赖，扩展通用图像融合能力。
- **Links / 链接**：[Paper](https://www.ieee-jas.com/article/doi/10.1109/JAS.2022.105686)
<a id="paper-seafusion"></a>

#### SeAFusion

- **Title / 标题**：Image Fusion in the Loop of High-Level Vision Tasks: A Semantic-Aware Real-Time Infrared and Visible Image Fusion Network
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：把语义任务反馈引入融合闭环，使红外—可见光融合更服务于高层视觉。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2210.09847) / [Code](https://github.com/Linfeng-Tang/SeAFusion)
<a id="paper-smfnet"></a>

#### Semantic-aware Multi-guided Fusion

- **Title / 标题**：A Semantic-Aware and Multi-Guided Network for Infrared-Visible Image Fusion
- **Year / 年份**：2024/2025
- **Core Contribution / 核心贡献**：通过语义感知和多重引导约束融合过程，强化融合图像的任务可用性。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2407.06159)
</details>

### 07. Image Generation & Editing / 图像生成与编辑

<details open>
<summary><strong>07.0 Quick Overview / 一页速览</strong></summary>

#### 07.0 一句话定位 / One-sentence Positioning

**图像生成**解决的是：如何让模型从随机噪声、文本、草图、布局、深度图、姿态、参考图等条件中生成新的图像。

它和传统感知任务的关系是：

```text
感知：从图像 → 语义
生成：从语义 / 条件 → 图像
```

图像生成不是和检测、分割无关的“画图工具”。它正在影响数据合成、仿真、风格迁移、图像编辑、三维生成、自动驾驶场景生成和机器人训练数据扩展。

---

</details>

<details>
<summary><strong>07.1 Basic Definition & Task Variants / 核心定义与任务变体</strong></summary>

#### Generation Taxonomy & Task Variants / 生成任务分类与任务变体

```text
Image Generation / 图像生成
├── Unconditional Generation / 无条件生成
├── Class-conditional Generation / 类别条件生成
├── Text-to-Image / 文本生成图像
├── Image-to-Image Translation / 图像到图像转换
├── Image Inpainting / 图像补全
├── Image Editing / 图像编辑
├── Personalized Generation / 个性化生成
├── Controllable Generation / 可控生成
│   ├── Edge-guided / 边缘引导
│   ├── Depth-guided / 深度引导
│   ├── Pose-guided / 姿态引导
│   ├── Segmentation-guided / 分割图引导
│   └── Layout-guided / 布局引导
├── Image Animation / 图像动画化
├── Video Generation / 视频生成
└── 3D-aware Generation / 三维感知生成
```

</details>

<details>
<summary><strong>07.2 Method Evolution / 方法演化主线</strong></summary>

#### 07.2.1 VAE 与 GAN：生成模型的早期主线 / VAE and GAN

VAE 强调概率建模和潜变量空间，GAN 强调对抗训练和视觉真实感。

GAN 的核心思想：

```text
生成器：努力生成假图骗过判别器
判别器：努力区分真实图和假图
二者对抗，生成器逐渐变强
```

GAN 时代的重要问题是：

```text
优点：图像锐利、视觉效果好
缺点：训练不稳定、模式崩溃、文本控制弱
```

StyleGAN 系列 把 GAN 的可控性和图像质量推到很高水平，尤其在人脸生成和风格空间分析中影响很大。

---

#### 07.2.2 Autoregressive 生成：把图像当序列 / Autoregressive Generation

自回归路线把图像离散化成 token，然后像语言模型一样逐步生成。

典型思想：

```text
图像 → 离散 token
按顺序预测下一个 token
token 序列 → 图像
```

这条路线和后来的 multimodal token、图像 tokenization、视觉自回归大模型有关系。

---

#### 07.2.3 Diffusion：从噪声逐步去噪 / Diffusion Models

扩散模型的直观理解：

```text
训练时：真实图像逐步加噪，学会如何反向去噪
生成时：从纯噪声开始，逐步去噪成图像
```

DDPM 的意义在于，让扩散模型成为高质量图像生成的主流路线之一。相比 GAN，扩散模型通常训练更稳定、模式覆盖更好，但采样速度较慢。

---

#### 07.2.4 Latent Diffusion：在潜空间里生成 / Latent Diffusion

像素空间生成成本很高。Latent Diffusion 的关键思想是：

```text
先用 Autoencoder 把图像压缩到潜空间
在潜空间里做扩散
最后再解码回图像
```

这大幅降低了高分辨率生成的计算成本，并成为 Stable Diffusion 等系统的重要基础。

---

#### 07.2.5 Text-to-Image：文本成为生成接口 / Text-to-Image

文本生成图像使“自然语言”成为生成模型的控制接口。DALL-E 2 使用 CLIP latent 作为中间表示；Imagen、Stable Diffusion、SDXL 等进一步推动了文本条件生成的质量和可用性。

这条主线的核心问题是：

```text
文本是否被正确理解？
主体是否稳定？
细节是否符合提示？
空间关系是否正确？
文字生成是否准确？
风格是否可控？
```

---

#### 07.2.6 Controllable Generation：从“会画”到“听指挥” / Controllable Generation

早期 text-to-image 最大问题是“会画但不听话”。ControlNet 的重要性在于，它让大规模预训练扩散模型接受额外空间条件，比如边缘、深度、姿态、分割图等。

可以这样理解：

```text
文本 prompt：告诉模型画什么
ControlNet 条件：告诉模型怎么摆、边界在哪、姿态如何、结构怎样
```

这使生成模型从“随机创作”走向“可控生产”。

---

#### 07.2.7 Image Editing：生成模型成为编辑器 / Image Editing

图像编辑方向包括：

```text
局部重绘 / Inpainting
指令编辑 / Instruction-based Editing
风格编辑 / Style Editing
对象替换 / Object Replacement
背景替换 / Background Replacement
图像扩展 / Outpainting
参考图驱动编辑 / Reference-guided Editing
```

这类任务和多模态大模型关系越来越强，因为用户往往通过语言描述编辑意图。

---

#### 07.2.8 生成与感知的合流 / Generation Meets Perception

近几年一个重要趋势是：生成模型不只是生成图片，也为视觉感知提供帮助。

```text
生成数据 → 训练检测/分割模型
生成场景 → 自动驾驶仿真
生成多视角 → 三维重建
生成视频 → 世界模型
生成图像编辑 → 数据增强
生成模型特征 → 开放词汇感知
```

</details>

<details>
<summary><strong>07.3 Upstream & Downstream / 上下游定位</strong></summary>

#### System Relevance / 与自动驾驶、具身智能和视觉任务的关系

#### 07.4.1 自动驾驶 / Autonomous Driving

生成模型在自动驾驶中可用于：

```text
场景生成
长尾 corner case 合成
天气 / 光照 / 风格迁移
多视角视频生成
世界模型
仿真数据增强
```

但是要注意：自动驾驶生成数据不能只看画质，必须看几何一致性、交通规则、时序一致性和闭环影响。

---

#### 07.4.2 具身智能 / Embodied AI

具身智能中，生成模型可用于：

```text
合成机器人训练数据
生成不同物体外观
生成任务场景
视频预测
语言指令到视觉目标
三维资产生成
```

但机器人最终要在真实世界执行动作，因此生成内容必须与物理规律、几何结构和可操作性一致。

---

#### 07.4.3 感知任务 / Perception Tasks

生成模型可以帮助检测、分割、跟踪，但也可能带来偏差：

```text
正面作用：
- 数据增强
- 长尾类别补充
- 稀有场景生成
- 预训练特征学习

风险：
- 幻觉细节
- 分布偏移
- 伪标签污染
- 生成数据过于干净或不真实
```

</details>

<details>
<summary><strong>07.4 Representative Works / 代表性工作速览</strong></summary>

| 年份 / Year | 方法 / Work | 位置 / Position | 为什么重要 / Why it matters |
|---:|---|---|---|
| 2014 | GAN | 对抗生成 | 奠定现代图像生成的重要路线 |
| 2015 | VAE | 概率生成 | 用潜变量建模图像分布 |
| 2017–2020 | StyleGAN 系列 | 高质量可控 GAN | 推动高保真人脸与风格空间分析 |
| 2020 | DDPM | 扩散生成 | 让扩散模型成为高质量图像生成主线 |
| 2021/2022 | Latent Diffusion | 高效扩散 | 在潜空间扩散，支撑 Stable Diffusion 类系统 |
| 2022 | DALL-E 2 | 文本图像生成 | 使用 CLIP latent 连接文本语义与图像生成 |
| 2022 | Imagen | 文本图像生成 | 强化语言模型与扩散生成结合 |
| 2023 | ControlNet | 可控生成 | 为扩散模型添加边缘、深度、姿态等空间控制 |
| 2023 | SDXL | 大规模 latent diffusion | 提升 Stable Diffusion 系列质量和条件建模 |
| 2024 | ControlNet++ | 控制一致性改进 | 用一致性反馈增强条件控制精度 |
| 2024–2025 | Diffusion Transformer / Flow Matching | 新一代生成骨干 | 从 U-Net 扩散逐步走向 DiT、流匹配和多模态统一生成 |

</details>

<details>
<summary><strong>07.5 Paper Positioning / 论文归位指引</strong></summary>

```text
1. 生成对象是什么？
   图像 / 视频 / 多视角 / 3D / 场景 / 机器人数据

2. 条件是什么？
   无条件 / 类别 / 文本 / 图像 / 边缘 / 深度 / 分割 / 姿态 / 布局 / 参考图

3. 方法路线是什么？
   GAN / VAE / Autoregressive / Diffusion / Latent Diffusion / DiT / Flow Matching

4. 解决什么问题？
   质量 / 可控性 / 一致性 / 速度 / 个性化 / 多视角一致 / 安全性

5. 下游用途是什么？
   艺术创作 / 数据增强 / 仿真 / 编辑 / 三维重建 / 世界模型
```

例子：

```text
一篇“ControlNet-like Model for Driving Scene Generation”论文
主任务：可控图像/视频生成
方法路线：扩散模型 + 条件控制
应用领域：自动驾驶仿真
关键问题：生成画质之外，还要保证多视角、交通语义和时序一致
```

</details>

<details>
<summary><strong>07.6 Paper Cards / 核心论文卡片</strong></summary>

> 本节集中放置本章代表论文入口。正文和代表论文表格中的方法名优先跳转到这里，外部 Paper / Code / Project 链接只在论文卡片中出现。

<a id="paper-gan"></a>

#### GAN

- **Title / 标题**：Generative Adversarial Nets
- **Year / 年份**：2014
- **Core Contribution / 核心贡献**：提出生成器与判别器的对抗训练框架，奠定现代深度生成模型的重要范式。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1406.2661)
<a id="paper-vae"></a>

#### VAE

- **Title / 标题**：Auto-Encoding Variational Bayes
- **Year / 年份**：2013/2014
- **Core Contribution / 核心贡献**：提出变分自编码框架，用潜变量概率建模连接生成学习与变分推断。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1312.6114)
<a id="paper-stylegan"></a>

#### StyleGAN 系列

- **Title / 标题**：A Style-Based Generator Architecture for Generative Adversarial Networks / Analyzing and Improving the Image Quality of StyleGAN / Alias-Free Generative Adversarial Networks
- **Year / 年份**：2019–2021
- **Core Contribution / 核心贡献**：通过风格调制生成器显著提升人脸图像生成质量和可控性。
- **Links / 链接**：[StyleGAN](https://arxiv.org/abs/1812.04948) / [StyleGAN2](https://arxiv.org/abs/1912.04958) / [StyleGAN3](https://arxiv.org/abs/2106.12423)
<a id="paper-ddpm"></a>

#### DDPM

- **Title / 标题**：Denoising Diffusion Probabilistic Models
- **Year / 年份**：2020
- **Core Contribution / 核心贡献**：用逐步去噪概率过程建模图像生成，推动扩散模型成为主流生成范式。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2006.11239)
<a id="paper-latent-diffusion"></a>

#### Latent Diffusion Models

- **Title / 标题**：High-Resolution Image Synthesis with Latent Diffusion Models
- **Year / 年份**：2021/2022
- **Core Contribution / 核心贡献**：将扩散过程迁移到潜空间，大幅降低高分辨率图像生成成本。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2112.10752) / [Code](https://github.com/CompVis/latent-diffusion)
<a id="paper-dalle2"></a>

#### DALL-E 2

- **Title / 标题**：Hierarchical Text-Conditional Image Generation with CLIP Latents
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：用 CLIP latent 与扩散模型连接文本语义和图像生成，提高文本到图像生成能力。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2204.06125)
<a id="paper-imagen"></a>

#### Imagen

- **Title / 标题**：Photorealistic Text-to-Image Diffusion Models with Deep Language Understanding
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：结合强语言模型和级联扩散模型，提升文本条件图像生成的语义一致性和真实感。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2205.11487)
<a id="paper-controlnet"></a>

#### ControlNet

- **Title / 标题**：Adding Conditional Control to Text-to-Image Diffusion Models
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：为文本到图像扩散模型加入结构化条件控制，支持姿态、边缘、深度等可控生成。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2302.05543) / [Code](https://github.com/lllyasviel/ControlNet)
<a id="paper-sdxl"></a>

#### SDXL

- **Title / 标题**：SDXL: Improving Latent Diffusion Models for High-Resolution Image Synthesis
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：通过更大的潜空间扩散架构和训练配方提升高分辨率文本图像生成质量。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2307.01952)
<a id="paper-controlnet-plus-plus"></a>

#### ControlNet++

- **Title / 标题**：Improving Conditional Controls with Efficient Consistency Feedback
- **Year / 年份**：2024
- **Core Contribution / 核心贡献**：用一致性反馈改进条件控制，使生成结果更遵循结构提示。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2404.07987)
<a id="paper-dit-flow-matching"></a>

#### Diffusion Transformer / Flow Matching

- **Title / 标题**：Scalable Diffusion Models with Transformers / Flow Matching for Generative Modeling
- **Year / 年份**：2022–2023
- **Core Contribution / 核心贡献**：将 Transformer 和连续流匹配目标引入生成建模，推动扩散/流模型的可扩展训练。
- **Links / 链接**：[DiT](https://arxiv.org/abs/2212.09748) / [Flow Matching](https://arxiv.org/abs/2210.02747)
</details>

### 08. 3D Vision & 3D Reconstruction / 三维视觉与三维重建

<details open>
<summary><strong>08.0 Quick Overview / 一页速览</strong></summary>

#### 08.0 一句话定位 / One-sentence Positioning

**三维视觉**解决的是：如何从图像、视频、点云或多视角观测中恢复世界的三维结构。

二维视觉问的是：

```text
图像里有什么？
```

三维视觉进一步问：

```text
它在哪里？
有多远？
形状是什么？
相机怎么动？
场景三维结构是什么？
```

它是自动驾驶、机器人、AR/VR、数字孪生、三维生成和空间智能的基础。

---

</details>

<details>
<summary><strong>08.1 Basic Definition & Task Variants / 核心定义与任务变体</strong></summary>

#### 3D Task Tree / 三维任务树

```text
3D Vision / 三维视觉
├── Depth Estimation / 深度估计
│   ├── Monocular Depth / 单目深度
│   ├── Stereo Depth / 双目深度
│   └── Multi-view Depth / 多视角深度
├── Stereo Matching / 立体匹配
├── Optical Flow & Scene Flow / 光流与场景流
├── Structure from Motion, SfM / 运动恢复结构
├── Multi-view Stereo, MVS / 多视图立体
├── Visual Odometry / 视觉里程计
├── SLAM / 同步定位与建图
├── 3D Reconstruction / 三维重建
│   ├── Point Cloud Reconstruction / 点云重建
│   ├── Mesh Reconstruction / 网格重建
│   ├── Voxel Reconstruction / 体素重建
│   └── Implicit Reconstruction / 隐式重建
├── Camera Pose Estimation / 相机位姿估计
├── 3D Object Detection / 三维目标检测
├── 3D Semantic Segmentation / 三维语义分割
└── Feed-forward 3D Foundation Models / 前馈式三维基础模型
```

</details>

<details>
<summary><strong>08.2 Method Evolution / 方法演化主线</strong></summary>

#### 08.2.1 几何视觉时代：相机、匹配、三角化 / Classical Geometric Vision

传统三维重建的核心链条是：

```text
特征点提取
→ 特征匹配
→ 相机位姿估计
→ 三角化
→ 稀疏点云
→ 多视图立体
→ 稠密点云 / 网格
```

典型系统包括 SfM、MVS、SLAM。它们高度依赖几何约束和优化，优点是可解释，缺点是对纹理少、光照变化、动态物体、弱匹配场景比较敏感。

---

#### 08.2.2 深度学习进入几何：从局部模块替换开始 / Learning-based Geometry

深度学习最初不是直接替代整个三维重建管线，而是替换其中某些模块：

```text
学习特征点
学习匹配
学习深度估计
学习立体匹配代价体
学习位姿估计
学习稠密重建
```

例如单目深度估计让一张图也能预测相对或绝对深度；学习型 stereo matching 用 CNN/Transformer 构建代价体；学习型 SLAM 尝试增强鲁棒性。

---

#### 08.2.3 隐式表示与神经场：从点云/网格到连续函数 / Implicit Representation

传统三维表示通常是点云、体素或网格，而隐式表示把三维结构表达成一个连续函数：

```text
输入：空间坐标
输出：占据概率 / SDF / 颜色 / 密度
```

这条路线连接到 Occupancy Networks / DeepSDF、NeRF 等工作。它的意义是：三维结构不再只是离散点或网格，也可以是可查询、可优化的连续场。

---

#### 08.2.4 DUSt3R：从“先标定再重建”到“直接预测三维关系” / DUSt3R-style Reconstruction

传统 MVS 往往需要已知或先估计相机参数，再做三角化和稠密匹配。DUSt3R 的关键意义在于：它提出从未标定、未定姿的图像集合中直接预测 dense 3D point maps，把许多几何步骤合并到学习模型中。

可以这样理解：

```text
传统管线：
图像 → 匹配 → 相机位姿 → 三角化 → 点云

DUSt3R 式路线：
图像对 / 图像集合 → 网络直接预测三维点图与几何关系
```

这不是简单“用 Transformer 做三维”，而是改变了三维重建的工作流。

---

#### 08.2.5 VGGT：前馈式通用三维几何模型 / Feed-forward 3D Geometry Foundation Model

VGGT 代表了另一个重要趋势：把相机参数、深度图、点图、点轨迹等关键三维属性统一交给一个前馈 Transformer 预测。

它的意义在于：

```text
过去：深度、相机、点云、跟踪是多个任务
现在：一个模型直接输出多种三维几何属性
```

这与视觉基础模型的逻辑相似：用大规模数据和统一架构学习通用几何先验。

</details>

<details>
<summary><strong>08.3 Upstream & Downstream / 上下游定位</strong></summary>

#### Relationship to Other Modules / 与其他模块的关系

#### 08.4.1 与自动驾驶 / Autonomous Driving

自动驾驶需要三维视觉回答：

```text
车辆和行人在哪里？
道路结构是什么？
可行驶空间在哪里？
遮挡区域有什么风险？
当前车的位姿在哪里？
```

相关任务包括 3D 检测、BEV 感知、Occupancy、在线建图和神经仿真。

---

#### 08.4.2 与具身智能 / Embodied AI

机器人需要三维视觉回答：

```text
物体在哪里？
能不能抓？
抓取点在哪里？
障碍物在哪里？
机器人如何在空间中移动？
```

因此三维重建和空间记忆是导航、操作、抓取和长期任务执行的基础。

---

#### 08.4.3 与图像生成 / Generation

生成模型正在进入三维：

```text
2D image generation
→ multi-view generation
→ 3D-aware generation
→ NeRF / 3DGS generation
→ dynamic 4D scene generation
```

这使“生成图像”和“生成三维世界”逐渐合流。

</details>

<details>
<summary><strong>08.4 Representative Works / 代表性工作速览</strong></summary>

| 年份 / Year | 方法 / Work | 位置 / Position | 为什么重要 / Why it matters |
|---:|---|---|---|
| 传统阶段 | SfM / Bundle Adjustment | 多视角几何 | 现代三维重建和摄影测量基础 |
| 传统阶段 | MVS | 稠密三维重建 | 从多视图图像恢复稠密表面 |
| 2015–2018 | CNN Depth / Stereo | 学习型深度与立体匹配 | 用深度网络替代手工代价或先验 |
| 2019 | DeepSDF / Occupancy Networks | 隐式三维表示 | 用连续函数表示形状和占据 |
| 2020 | NeRF | 神经辐射场 | 将新视角合成与三维场表示结合 |
| 2023 | 3D Gaussian Splatting | 显式可渲染三维表示 | 兼顾质量、速度和实时渲染 |
| 2024 | DUSt3R | 前馈式稠密三维重建 | 从未标定图像直接预测 dense 3D point maps |
| 2024 | MASt3R | 3D grounding image matching | 将图像匹配与三维几何进一步结合 |
| 2025 | VGGT | 通用三维几何前馈模型 | 统一预测相机、深度、点图、点轨迹等关键三维属性 |
| 2025 | MUSt3R | 多视角 DUSt3R 扩展 | 面向大规模多视角三维重建的扩展 |

</details>

<details>
<summary><strong>08.5 Paper Positioning / 论文归位指引</strong></summary>

```text
1. 输入是什么？
   单张图像 / 双目 / 多视图 / 视频 / 点云 / RGB-D / 未标定图像集合

2. 输出是什么？
   深度 / 相机位姿 / 点云 / 网格 / 隐式场 / 3DGS / 轨迹 / 语义三维图

3. 方法属于哪条路线？
   几何优化 / 学习深度 / 学习匹配 / 隐式表示 / 神经渲染 / 前馈式三维基础模型

4. 是否需要相机参数？
   已知相机 / 先估计相机 / 不需要显式相机输入

5. 下游用途是什么？
   新视角合成 / 自动驾驶 / 机器人 / AR/VR / 数字孪生 / 三维生成
```

例子：

```text
一篇“Transformer-based Feed-forward 3D Reconstruction”论文
主任务：三维重建
方法路线：前馈式几何模型
关键问题：减少传统 SfM/MVS 管线依赖
下游意义：让三维重建更接近通用视觉基础模型
```

</details>

<details>
<summary><strong>08.6 Paper Cards / 核心论文卡片</strong></summary>

> 本节集中放置本章代表论文入口。正文和代表论文表格中的方法名优先跳转到这里，外部 Paper / Code / Project 链接只在论文卡片中出现。

<a id="paper-mvsnet"></a>

#### MVSNet

- **Title / 标题**：MVSNet: Depth Inference for Unstructured Multi-view Stereo
- **Year / 年份**：2018
- **Core Contribution / 核心贡献**：用可微代价体和 3D CNN 实现端到端多视角深度估计。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1804.02505) / [Code](https://github.com/YoYo000/MVSNet)
<a id="paper-deepsdf-occupancy-networks"></a>

#### DeepSDF / Occupancy Networks

- **Title / 标题**：DeepSDF: Learning Continuous Signed Distance Functions for Shape Representation / Occupancy Networks: Learning 3D Reconstruction in Function Space
- **Year / 年份**：2019
- **Core Contribution / 核心贡献**：用连续隐式函数表示三维形状，摆脱固定体素分辨率限制。
- **Links / 链接**：[DeepSDF](https://arxiv.org/abs/1901.05103) / [Occupancy Networks](https://arxiv.org/abs/1812.03828)
<a id="paper-nerf"></a>

#### NeRF

- **Title / 标题**：Representing Scenes as Neural Radiance Fields for View Synthesis
- **Year / 年份**：2020
- **Core Contribution / 核心贡献**：用神经辐射场表示三维场景，实现基于多视角图像的新视角合成。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2003.08934) / [Project](https://www.matthewtancik.com/nerf)
<a id="paper-3dgs"></a>

#### 3D Gaussian Splatting

- **Title / 标题**：3D Gaussian Splatting for Real-Time Radiance Field Rendering
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：用显式三维高斯表示和可微 splatting 实现实时高质量神经渲染。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2308.04079) / [Project](https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/)
<a id="paper-dust3r"></a>

#### DUSt3R

- **Title / 标题**：DUSt3R: Geometric 3D Vision Made Easy
- **Year / 年份**：2024
- **Core Contribution / 核心贡献**：将多视图几何重建转化为端到端网络预测，降低传统 SfM/MVS 流程复杂度。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2312.14132) / [Code](https://github.com/naver/dust3r)
<a id="paper-mast3r"></a>

#### MASt3R

- **Title / 标题**：Grounding Image Matching in 3D with MASt3R
- **Year / 年份**：2024
- **Core Contribution / 核心贡献**：把图像匹配显式 grounding 到三维几何中，增强多视角重建的匹配可靠性。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2406.09756) / [Code](https://github.com/naver/mast3r)
<a id="paper-vggt"></a>

#### VGGT

- **Title / 标题**：VGGT: Visual Geometry Grounded Transformer
- **Year / 年份**：2025
- **Core Contribution / 核心贡献**：用视觉几何 Transformer 统一预测相机、深度和点轨迹等几何要素。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2503.11651) / [Project](https://vgg-t.github.io/) / [Code](https://github.com/facebookresearch/vggt)
<a id="paper-must3r"></a>

#### MUSt3R

- **Title / 标题**：MUSt3R: Multi-view Network for Stereo 3D Reconstruction
- **Year / 年份**：2025
- **Core Contribution / 核心贡献**：面向多视图立体重建设计统一网络，提升稠密三维恢复效率。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2503.01661) / [Code](https://github.com/naver/must3r)
</details>

### 09. NeRF, 3D Gaussian Splatting & Neural Rendering / NeRF、3DGS 与神经渲染

<details open>
<summary><strong>09.0 Quick Overview / 一页速览</strong></summary>

#### 09.0 一句话定位 / One-sentence Positioning

**NeRF 和 3DGS** 解决的是：如何从一组图像中学习一个可以从新视角渲染的三维场景表示。

它和普通三维重建的区别是：

```text
普通重建：更关心几何形状
神经渲染：同时关心几何、颜色、光照和新视角真实感
```

---

</details>

<details>
<summary><strong>09.1 Basic Definition & Task Variants / 核心定义与任务变体</strong></summary>

#### Basic Concepts & Task Variants / 基本概念与任务变体

#### 09.1.1 NeRF 是什么 / What is NeRF?

NeRF 把场景表示成一个连续函数：

```text
输入：三维坐标 x,y,z + 观察方向
输出：颜色 RGB + 体密度 density
```

然后通过体渲染从任意相机视角合成图像。

直观理解：

```text
不是显式存一个网格
而是训练一个网络，让它知道空间中每个位置是什么颜色、是否有东西
```

---

#### 09.1.2 3D Gaussian Splatting 是什么 / What is 3DGS?

3DGS 用大量可优化的三维高斯椭球表示场景。每个高斯带有位置、形状、透明度、颜色等参数，渲染时把这些高斯投影到图像平面。

直观理解：

```text
NeRF：用神经网络查询空间点
3DGS：用一堆可渲染的三维高斯直接表示场景
```

3DGS 的优势是训练和渲染速度快，尤其适合实时新视角合成和交互式场景浏览。

</details>

<details>
<summary><strong>09.2 Method Evolution / 方法演化主线</strong></summary>

#### 09.2.1 NeRF：高质量但慢 / NeRF Baseline

NeRF 的贡献是把多视角图像、新视角合成、体渲染和神经场结合起来。它打开了“用神经网络表示场景”的研究热潮。

问题是：

```text
训练慢
渲染慢
需要已知相机位姿
动态场景困难
大场景困难
几何可编辑性弱
```

---

#### 09.2.2 NeRF 加速：让神经场可用 / Fast NeRF

后续大量工作围绕加速展开：

```text
Mip-NeRF：抗锯齿与尺度建模
Mip-NeRF 360：无界大场景
PlenOctrees / TensoRF：更高效表示
Instant-NGP：多分辨率哈希编码，加速训练和渲染
```

Instant-NGP 的意义是非常清楚的：通过多分辨率哈希编码，把原本慢速优化的神经场显著加速。

---

#### 09.2.3 Generalizable NeRF：从每个场景训练到跨场景泛化 / Generalizable NeRF

原始 NeRF 通常每个场景单独训练。Generalizable NeRF 想要：

```text
在很多场景上训练一个模型
新场景只需少量视角
无需长时间重新优化
```

这条路线对机器人和自动驾驶很重要，因为现实系统不能为每个新场景慢慢训练一个 NeRF。

---

#### 09.2.4 Dynamic NeRF：从静态场景到动态世界 / Dynamic Neural Fields

现实世界会动。动态 NeRF / 4D NeRF 试图表示：

```text
空间 + 时间
物体运动
人体动作
动态交通场景
可交互环境
```

这条路线和世界模型、视频生成、具身智能仿真高度相关。

---

#### 09.2.5 3D Gaussian Splatting：从隐式查询到显式 splat / 3DGS

3DGS 的关键转变是：不再每次渲染都密集查询 MLP，而是直接优化一组可渲染的 3D Gaussians，并使用高效的可见性排序和 splatting 渲染。

因此它成为近两年非常重要的三维表达：

```text
NeRF：质量高，但渲染慢
3DGS：质量高，同时更接近实时交互
```

---

#### 09.2.6 3DGS 后续方向 / After 3DGS

3DGS 后续方向可以分成：

```text
Dynamic 3DGS / 动态高斯
Semantic 3DGS / 语义高斯
Editable 3DGS / 可编辑高斯
Generative 3DGS / 生成式高斯
Large-scale 3DGS / 大场景高斯
Driving 3DGS / 自动驾驶场景高斯
Embodied 3DGS / 具身环境建模
```

新手要知道：3DGS 不是“替代所有三维重建”的唯一答案。它在新视角合成和可视化上很强，但几何精度、物理可交互性、动态一致性、语义理解仍是活跃问题。

</details>

<details>
<summary><strong>09.3 Upstream & Downstream / 上下游定位</strong></summary>

#### Relationship to Simulation, Driving and Embodied AI / 与仿真、自动驾驶、具身智能关系

#### 09.4.1 自动驾驶仿真 / Driving Simulation

NeRF / 3DGS 可用于：

```text
真实道路场景重建
新视角合成
传感器仿真
corner case 重放
闭环仿真环境
数据增强
```

但自动驾驶需要的不只是漂亮画面，还要：

```text
几何准确
动态对象可控
交通参与者可交互
传感器物理一致
语义标注可用
```

---

#### 09.4.2 具身智能环境建模 / Embodied Environment Modeling

机器人场景中，NeRF / 3DGS 可用于构建可视化三维记忆，但机器人还需要知道：

```text
哪里可行走？
哪里可抓取？
物体能否移动？
接触后会怎样？
```

因此神经渲染要和语义、物理、可供性、动作模型结合，才能成为真正的具身世界模型。

---

#### 09.4.3 AR/VR 与数字孪生 / AR/VR and Digital Twin

3DGS 的实时渲染特性使它很适合：

```text
AR/VR 场景捕捉
虚拟旅游
房地产展示
游戏资产
文化遗产数字化
数字孪生
```

</details>

<details>
<summary><strong>09.4 Representative Works / 代表性工作速览</strong></summary>

| 年份 / Year | 方法 / Work | 位置 / Position | 为什么重要 / Why it matters |
|---:|---|---|---|
| 2020 | NeRF | 神经辐射场起点 | 用连续体渲染函数实现高质量新视角合成 |
| 2021 | Mip-NeRF | 抗锯齿 NeRF | 解决不同尺度采样和 aliasing 问题 |
| 2022 | Mip-NeRF 360 | 无界场景 NeRF | 推动大范围真实场景新视角合成 |
| 2022 | TensoRF | 张量分解 NeRF | 用张量表示提升效率 |
| 2022 | Instant-NGP | 快速神经图形基元 | 用多分辨率哈希编码大幅加速训练 |
| 2023 | 3D Gaussian Splatting | 实时辐射场渲染 | 用可优化三维高斯实现高质量实时渲染 |
| 2023–2025 | Dynamic 3DGS | 动态场景 | 将高斯表示扩展到时间维度 |
| 2024–2025 | Driving / Urban 3DGS | 城市场景与自动驾驶 | 将 3DGS 用于街景重建、仿真和数据生成 |
| 2024–2025 | Generative 3DGS | 三维生成 | 将生成模型和高斯表示结合 |

</details>

<details>
<summary><strong>09.5 Paper Positioning / 论文归位指引</strong></summary>

```text
1. 表示方式是什么？
   MLP NeRF / voxel / tensor / hash grid / 3D Gaussian / hybrid

2. 场景类型是什么？
   物体级 / 室内 / 室外 / 城市 / 自动驾驶 / 人体 / 动态场景

3. 目标是什么？
   新视角合成 / 几何重建 / 实时渲染 / 动态建模 / 语义理解 / 可编辑

4. 是否需要每场景优化？
   每场景训练 / 泛化模型 / 前馈预测 / 少样本适配

5. 与系统关系是什么？
   可视化 / 仿真 / 机器人地图 / 世界模型 / 数据生成
```

例子：

```text
一篇“3DGS for Autonomous Driving Simulation”论文
主任务：神经渲染 / 场景重建
应用域：自动驾驶仿真
核心问题：真实街景快速重建与新视角合成
需要额外关注：动态车辆、语义标注、传感器一致性、闭环评估
```

</details>

<details>
<summary><strong>09.6 Paper Cards / 核心论文卡片</strong></summary>

> 本节集中放置本章代表论文入口。正文和代表论文表格中的方法名优先跳转到这里，外部 Paper / Code / Project 链接只在论文卡片中出现。

- NeRF：见 08 章论文卡片。
- 3D Gaussian Splatting：见 08 章论文卡片。

<a id="paper-mip-nerf"></a>

#### Mip-NeRF

- **Title / 标题**：Mip-NeRF: A Multiscale Representation for Anti-Aliasing Neural Radiance Fields
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：用多尺度锥体积分抗锯齿表示，改善 NeRF 的尺度变化和采样混叠。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2103.13415)
<a id="paper-mip-nerf-360"></a>

#### Mip-NeRF 360

- **Title / 标题**：Mip-NeRF 360: Unbounded Anti-Aliased Neural Radiance Fields
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：扩展 NeRF 到无界 360 度场景，并改进远近尺度下的抗锯齿建模。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2111.12077) / [Project](https://jonbarron.info/mipnerf360/)
<a id="paper-tensorf"></a>

#### TensoRF

- **Title / 标题**：TensoRF: Tensorial Radiance Fields
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：用张量分解表示辐射场，显著降低 NeRF 训练与存储成本。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2203.09517) / [Code](https://github.com/apchenstu/TensoRF)
<a id="paper-instant-ngp"></a>

#### Instant-NGP

- **Title / 标题**：Instant Neural Graphics Primitives with a Multiresolution Hash Encoding
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：用多分辨率哈希编码加速神经图形基元训练，实现近实时优化。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2201.05989) / [Code](https://github.com/NVlabs/instant-ngp)
</details>

### 10. Point Cloud, BEV & Occupancy / 点云、BEV 与 Occupancy

<details open>
<summary><strong>10.0 Quick Overview / 一页速览</strong></summary>

#### 10.0 一句话定位 / One-sentence Positioning

**点云、BEV 和 Occupancy** 解决的是：如何把三维世界组织成适合机器感知、预测和规划的空间表示。

它们的区别可以粗略理解为：

```text
Point Cloud / 点云：世界由稀疏三维点组成
BEV / 鸟瞰图：把三维世界压到俯视平面上理解
Occupancy / 占据：把三维空间划成网格，判断每个格子是否被占据以及是什么类别
```

自动驾驶近年的感知主线正在从“检测几个 3D 框”走向“理解整个三维空间”。

---

</details>

<details>
<summary><strong>10.1 Basic Definition & Task Variants / 核心定义与任务变体</strong></summary>

本章主要围绕该领域的核心任务定义、常见输入输出形式和任务变体展开。

</details>

<details>
<summary><strong>10.2 Method Evolution / 方法演化主线</strong></summary>

#### 10.2.1 Point Cloud Perception / 点云感知

##### 10.2.1.1 点云任务 / Tasks

```text
Point Cloud Perception / 点云感知
├── Point Cloud Classification / 点云分类
├── Point Cloud Segmentation / 点云分割
├── 3D Object Detection / 三维目标检测
├── Point Cloud Completion / 点云补全
├── Point Cloud Registration / 点云配准
├── LiDAR Odometry / 激光雷达里程计
└── Point Cloud Scene Understanding / 点云场景理解
```

##### 10.2.1.2 方法演化 / Method Evolution

点云不规则、无序、稀疏，因此不能像图像一样直接用普通卷积处理。

典型路线：

```text
Point-based：PointNet → PointNet++
Voxel-based：VoxelNet → SECOND
Pillar-based：PointPillars
Point-Voxel Hybrid：PV-RCNN
Center-based：CenterPoint
Transformer-based：Point Transformer / 3D Transformer
Multi-modal：LiDAR-Camera Fusion
```

##### PointNet 的意义

PointNet 的关键贡献是直接处理无序点集，用对称函数聚合点特征，让深度网络可以直接吃点云。

##### VoxelNet / SECOND 的意义

Voxel-based 方法把点云划成体素，使稀疏三维卷积成为可能，更适合大规模 3D 检测。

##### PointPillars 的意义

PointPillars 把点云组织成柱状 pillar，再用 2D CNN 处理 BEV 特征，是自动驾驶 3D 检测中兼顾速度和精度的代表路线。

##### CenterPoint 的意义

CenterPoint 把 3D 检测转化成中心点检测，类似 CenterNet 在 2D 中的思想，成为 LiDAR 3D 检测的强基线。

#### 10.2.2 BEV Representation / BEV 表征

##### 10.2.2.1 BEV 是什么 / What is BEV?

BEV 是 Bird's-Eye View，即鸟瞰图表示。它把周围环境组织成俯视空间。

自动驾驶为什么喜欢 BEV？

```text
车辆运动发生在地面平面上
规划天然需要俯视空间
多摄像头信息可以统一到同一坐标系
地图、检测、车道线、轨迹预测都适合放在 BEV 中
```

##### 10.2.2.2 BEV 方法主线 / BEV Method Evolution

```text
LiDAR BEV
→ Camera BEV
→ Multi-camera BEV
→ Transformer BEV
→ Multi-modal BEV
→ Planning-oriented BEV
```

早期 BEV 多来自 LiDAR 或投影几何；后来多摄像头 BEV 成为主流方向之一。BEVFormer 的代表性意义在于，用 BEV queries 和时空 Transformer 从多摄像头图像中构建 BEV 表征。BEVFusion 则强调把多传感器信息统一到 BEV 空间，服务 3D 检测和 BEV 地图分割。

##### 10.2.2.3 BEV 的限制 / Limitations

BEV 很适合道路场景，但它把高度维压缩了，因此对立交桥、悬挂物、复杂三维结构表达不足。这也是 Occupancy 兴起的原因之一。

#### 10.2.3 Occupancy Perception / 占据感知

##### 10.2.3.1 Occupancy 是什么 / What is Occupancy?

Occupancy 把三维空间划分成体素网格，每个格子回答：

```text
这里有没有东西？
如果有，是什么类别？
是否可行驶？
是否被遮挡？
未来会不会被占据？
```

相比 3D detection，occupancy 的优势是：

```text
不仅描述车、人、障碍物这些离散目标
也描述道路、建筑、植被、未知区域、遮挡区域等连续空间
```

##### 10.2.3.2 为什么自动驾驶需要 Occupancy / Why Driving Needs Occupancy

3D 检测框只能描述有限类别目标，但规划需要知道：

```text
哪里可以走？
哪里不能走？
哪里被遮挡？
哪里可能有未知障碍？
路边异形障碍物怎么处理？
未见过类别怎么办？
```

Occupancy 更接近“规划可用的世界模型”。

##### 10.2.3.3 方法主线 / Method Evolution

```text
2D BEV Segmentation
→ 3D Semantic Occupancy
→ Camera-only Occupancy
→ LiDAR-based Occupancy
→ Multi-modal Occupancy
→ 4D Occupancy / Occupancy Flow
→ Planning-oriented Occupancy
```

代表性工作包括：

```text
VoxFormer：从图像预测三维占据
SurroundOcc：环视三维占据
OccFormer：将 BEV 扩展到 3D semantic occupancy
OpenOccupancy：构建大规模环视语义占据 benchmark
UniAD：将 occupancy、预测、规划放在统一自动驾驶系统中
```

#### 10.2.4 Multi-modal 3D Perception / 多模态三维感知

多模态三维感知回答的是：

```text
相机语义强，但距离不准；
LiDAR 距离准，但语义弱、稀疏；
Radar 速度强，恶劣天气更鲁棒；
地图有先验，但可能过时。
如何融合？
```

典型路线：

```text
Camera-LiDAR Fusion / 相机-激光雷达融合
├── Point-level Fusion / 点级融合
├── Feature-level Fusion / 特征级融合
├── BEV-level Fusion / BEV级融合
└── Query-based Fusion / 查询式融合

Camera-Radar Fusion / 相机-雷达融合
├── 速度信息补充
├── 恶劣天气鲁棒性
└── 稀疏雷达点与图像语义对齐

Map Fusion / 地图融合
├── HD Map 辅助感知
├── Online Map Construction
└── Mapless / Map-light Driving
```

多模态检测也应该挂在这里，而不是只挂在目标检测下面。具体的检测方法主线可回看 **02.1 / 02.2 目标检测的任务变体与方法演化**；本节关注它们进入三维空间与自动驾驶系统后的融合位置。

```text
多模态目标检测
→ 多模态三维感知
→ 自动驾驶感知系统
```

</details>

<details>
<summary><strong>10.3 Upstream & Downstream / 上下游定位</strong></summary>

点云、BEV 与 Occupancy 是自动驾驶和机器人系统中的空间中间表示，负责把传感器观测转换成可用于规划的几何世界。

```text
上游输入：LiDAR 点云、多相机图像、Radar、深度、位姿、标定、HD Map 或在线地图
本章输出：3D boxes、点云语义、BEV feature / BEV map、3D occupancy、occupancy flow
下游模块：多目标跟踪、轨迹预测、可行驶区域判断、碰撞检查、规划控制、仿真评估
系统价值：把“看到什么”推进到“空间中哪里可走、哪里被占据、未来可能怎样变化”
```

因此，点云/BEV/Occupancy 论文不要只按检测精度归类，还要看它的空间表达是否能稳定服务预测、规划和闭环评估。

</details>

<details>
<summary><strong>10.4 Representative Works / 代表性工作速览</strong></summary>

| 年份 / Year | 方法 / Work | 位置 / Position | 为什么重要 / Why it matters |
|---:|---|---|---|
| 2017 | PointNet | 点云深度学习起点 | 直接处理无序点集 |
| 2017 | PointNet++ | 局部层次点云特征 | 解决 PointNet 局部结构建模不足 |
| 2018 | VoxelNet | 体素 3D 检测 | 将点云体素化并用于 3D detection |
| 2018 | SECOND | 稀疏卷积 3D 检测 | 提升体素检测效率 |
| 2019 | PointPillars | 高效 LiDAR 检测 | 用 pillar 表示和 2D CNN 实现高效检测 |
| 2020 | PV-RCNN | 点-体素融合 | 结合 voxel 全局特征与 point 细节 |
| 2021 | CenterPoint | 中心点 3D 检测 | 将 3D 检测转为中心点检测与跟踪 |
| 2022 | BEVFormer | Camera-only BEV | 用时空 Transformer 构建 BEV 表征 |
| 2022 | BEVFusion | 多模态 BEV 融合 | 将多传感器融合到 BEV 空间 |
| 2023 | VoxFormer | Camera-based occupancy | 从单/多相机图像恢复三维语义占据 |
| 2023 | SurroundOcc | Multi-camera occupancy | 面向环视相机的 3D occupancy 预测 |
| 2023 | OccFormer | Vision-based semantic occupancy | 用双路径 Transformer 建模三维语义占据 |
| 2023 | OpenOccupancy | Occupancy Benchmark | 提供大规模环视语义占据 benchmark |
| 2023 | UniAD | 规划导向自动驾驶 | 将感知、预测、规划统一到规划导向系统中 |
| 2024–2025 | 4D Occupancy / Occupancy Flow | 动态占据 | 从静态空间理解走向时空世界建模 |

</details>

<details>
<summary><strong>10.5 Paper Positioning / 论文归位指引</strong></summary>

```text
1. 输入模态是什么？
   LiDAR / Camera / Radar / Multi-camera / Multi-modal / Map

2. 空间表示是什么？
   Point cloud / Voxel / Pillar / BEV / Occupancy / Latent world state

3. 输出是什么？
   3D box / BEV segmentation / semantic occupancy / occupancy flow / planning trajectory

4. 主要解决什么问题？
   稀疏性 / 深度不确定 / 多模态对齐 / 遮挡 / 高度结构 / 计算成本 / 规划适配

5. 下游任务是什么？
   3D 检测 / 地图构建 / 轨迹预测 / 运动规划 / 仿真 / 安全验证
```

例子：

```text
一篇“Camera-only 3D Occupancy Prediction”论文
主任务：三维占据感知
输入：多摄像头图像
核心问题：从 2D 图像恢复 3D 空间占据
方法难点：深度估计、遮挡、体素分辨率、计算成本
下游意义：比 3D box 更适合规划与安全约束
```

</details>

<details>
<summary><strong>10.6 Paper Cards / 核心论文卡片</strong></summary>

> 本节集中放置本章代表论文入口。正文和代表论文表格中的方法名优先跳转到这里，外部 Paper / Code / Project 链接只在论文卡片中出现。

<a id="paper-pointnet"></a>

#### PointNet

- **Title / 标题**：PointNet: Deep Learning on Point Sets for 3D Classification and Segmentation
- **Year / 年份**：2017
- **Core Contribution / 核心贡献**：直接在无序点集上学习特征，开创深度点云识别路线。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1612.00593) / [Project](https://stanford.edu/~rqi/pointnet/)
<a id="paper-pointnet-plus-plus"></a>

#### PointNet++

- **Title / 标题**：PointNet++: Deep Hierarchical Feature Learning on Point Sets in a Metric Space
- **Year / 年份**：2017
- **Core Contribution / 核心贡献**：通过层次化局部区域学习改进 PointNet 对局部几何结构的建模。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1706.02413)
<a id="paper-voxelnet"></a>

#### VoxelNet

- **Title / 标题**：VoxelNet: End-to-End Learning for Point Cloud Based 3D Object Detection
- **Year / 年份**：2018
- **Core Contribution / 核心贡献**：将点云体素化并端到端学习三维检测特征，开启深度点云检测路线。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1711.06396)
<a id="paper-second"></a>

#### SECOND

- **Title / 标题**：SECOND: Sparsely Embedded Convolutional Detection
- **Year / 年份**：2018
- **Core Contribution / 核心贡献**：用稀疏卷积加速体素特征提取，提高三维点云检测效率。
- **Links / 链接**：[Paper](https://www.mdpi.com/1424-8220/18/10/3337)
<a id="paper-pointpillars"></a>

#### PointPillars

- **Title / 标题**：PointPillars: Fast Encoders for Object Detection from Point Clouds
- **Year / 年份**：2019
- **Core Contribution / 核心贡献**：用柱状体表示将点云检测转化为高效 BEV 伪图像处理。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1812.05784)
<a id="paper-pv-rcnn"></a>

#### PV-RCNN / PV-RCNN++

- **Title / 标题**：PV-RCNN: Point-Voxel Feature Set Abstraction for 3D Object Detection / PV-RCNN++: Point-Voxel Feature Set Abstraction With Local Vector Representation
- **Year / 年份**：2020–2021
- **Core Contribution / 核心贡献**：融合点级和体素级特征，提升三维检测的定位与语义表达能力。
- **Links / 链接**：[PV-RCNN](https://arxiv.org/abs/1912.13192) / [PV-RCNN++](https://arxiv.org/abs/2102.00463)
<a id="paper-centerpoint"></a>

#### CenterPoint

- **Title / 标题**：Center-Based 3D Object Detection and Tracking
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：将三维检测转化为 BEV 中心点预测，并自然连接检测与跟踪。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2006.11275) / [Code](https://github.com/tianweiy/CenterPoint)
<a id="paper-bevformer"></a>

#### BEVFormer

- **Title / 标题**：BEVFormer: Learning Bird's-Eye-View Representation from Multi-Camera Images via Spatiotemporal Transformers
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：用 BEV queries 和时空注意力从多摄像头图像中构建 BEV 表征，并通过历史 BEV 融合提升时序一致性。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2203.17270) / [Code](https://github.com/fundamentalvision/BEVFormer)
<a id="paper-bevfusion"></a>

#### BEVFusion

- **Title / 标题**：BEVFusion: Multi-Task Multi-Sensor Fusion with Unified Bird's-Eye View Representation
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：在统一 BEV 空间融合相机与 LiDAR 等多传感器特征，同时支持 3D 检测和 BEV 语义地图等多任务。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2205.13542) / [Code](https://github.com/mit-han-lab/bevfusion)
<a id="paper-voxformer"></a>

#### VoxFormer

- **Title / 标题**：VoxFormer: Sparse Voxel Transformer for Camera-based 3D Semantic Scene Completion
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：提出从 2D 图像生成稀疏 voxel proposals，再用 Transformer 完成三维语义场景补全的 camera-only occupancy 路线。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2302.12251) / [Code](https://github.com/NVlabs/VoxFormer)
<a id="paper-surroundocc"></a>

#### SurroundOcc

- **Title / 标题**：SurroundOcc: Multi-Camera 3D Occupancy Prediction for Autonomous Driving
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：将场景理解推进到三维占据预测，增强自动驾驶对空间可通行性和动态环境的建模。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2303.09551) / [Code](https://github.com/weiyithu/SurroundOcc)
<a id="paper-occformer"></a>

#### OccFormer

- **Title / 标题**：OccFormer: Dual-path Transformer for Vision-based 3D Semantic Occupancy Prediction
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：用双路径 Transformer 同时建模局部语义和全局几何，把环视图像语义提升到 3D semantic occupancy。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2304.05316)
<a id="paper-openoccupancy"></a>

#### OpenOccupancy

- **Title / 标题**：OpenOccupancy: A Large Scale Benchmark for Surrounding Semantic Occupancy Perception
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：将场景理解推进到三维占据预测，增强自动驾驶对空间可通行性和动态环境的建模。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2303.03991) / [Code](https://github.com/JeffWang987/OpenOccupancy)
<a id="paper-uniad"></a>

#### UniAD

- **Title / 标题**：Planning-oriented Autonomous Driving
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：将检测、跟踪、建图、运动预测、occupancy 与规划组织成规划导向的端到端自动驾驶框架，用规划质量反向约束上游模块。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2212.10156) / [Code](https://github.com/OpenDriveLab/UniAD)
</details>

## Part III. Text, Multimodal & Open-world Perception / 文档、多模态与开放世界感知

### 11. OCR & Document Understanding / OCR 与文档理解

<details open>
<summary><strong>11.0 Quick Overview / 一页速览</strong></summary>

```text
OCR & Document Understanding / OCR 与文档理解

├── 1. Scene Text / 场景文字
│   ├── Text Detection / 文本检测：文字在哪里？
│   ├── Text Recognition / 文本识别：文字内容是什么？
│   ├── Text Spotting / 端到端文字识别：同时检测和识别
│   └── Text-aware VQA / 文字感知视觉问答
│
├── 2. Document AI / 文档智能
│   ├── Layout Analysis / 版面分析
│   ├── Table Recognition / 表格识别
│   ├── Form Understanding / 表单理解
│   ├── Chart Understanding / 图表理解
│   ├── Document VQA / 文档问答
│   └── Structured Extraction / 结构化信息抽取
│
├── 3. Method Evolution / 方法演化
│   ├── 传统图像处理 + 字符分类
│   ├── CNN / CRNN / CTC
│   ├── Attention-based Recognition
│   ├── Transformer OCR
│   ├── LayoutLM-style 文档预训练
│   └── Donut / Pix2Struct / MLLM 文档理解
│
└── 4. System Role / 系统位置
    ├── 自动驾驶：交通标志、路牌、车牌、文字提示
    ├── 机器人：阅读标签、说明书、屏幕、按钮文字
    ├── 办公自动化：票据、合同、表单、报告
    └── 多模态大模型：图像中可读文本的语义理解
```

</details>

<details>
<summary><strong>11.1 Basic Definition & Task Variants / 核心定义与任务变体</strong></summary>

#### OCR Is Not Just Text Recognition / OCR 不只是文字识别

很多人以为 OCR 只是“识别图片里的文字”。但完整的 OCR / 文档理解通常包括：

```text
文字区域检测 → 文本行识别 → 阅读顺序恢复 → 版面结构理解 → 表格/图表解析 → 结构化输出
```

场景文字和文档文字也不同：

```text
Scene Text / 场景文字：街景、广告牌、车牌、商品包装、路牌，形变大、光照复杂。
Document Text / 文档文字：PDF、票据、合同、表格、扫描件，结构复杂、信息密集。
```

#### Main Tasks / 主要任务

| 任务 Task | 中文解释 | 输出 |
|---|---|---|
| Text Detection | 文本检测 | 文字框 / 多边形区域 |
| Text Recognition | 文本识别 | 字符串 |
| Text Spotting | 端到端文字识别 | 文本位置 + 内容 |
| Layout Analysis | 版面分析 | 标题、段落、表格、图像等版面块 |
| Table Recognition | 表格识别 | 单元格结构、行列关系、HTML/Markdown 表格 |
| Form Understanding | 表单理解 | key-value 字段 |
| Chart Understanding | 图表理解 | 图表类型、数据、趋势、问答 |
| Document VQA | 文档问答 | 根据文档图像回答问题 |

</details>

<details>
<summary><strong>11.2 Method Evolution / 方法演化主线</strong></summary>

#### 11.2.1 Traditional OCR / 传统 OCR

传统 OCR 依赖图像二值化、连通域分析、字符切分和字符分类。它在扫描质量好、排版规则的文档中有效，但很难处理自然场景中的弯曲文字、遮挡、低光、复杂背景。

#### 11.2.2 CNN / CRNN / CTC：从字符切分到序列识别

CRNN + CTC 是 OCR 中非常重要的路线。它不再强制先切出每个字符，而是把文本行当作序列进行识别。CTC 可以在不知道字符精确位置的情况下训练序列模型。

#### 11.2.3 Attention & Transformer OCR / 注意力与 Transformer OCR

Attention-based OCR 把识别过程看作序列解码；Transformer OCR 进一步增强长程依赖建模，对复杂文本形态更友好。

#### 11.2.4 Layout-aware Pretraining / 版面感知预训练

文档理解不仅要看文字内容，还要看位置和版面结构。LayoutLM 类模型把文本、坐标、视觉特征结合起来，使模型理解“哪个字段属于哪个表格/标题/段落”。

#### 11.2.5 OCR-free Document Understanding / 无显式 OCR 的文档理解

Donut、Pix2Struct 等路线尝试直接从文档图像生成结构化文本，不一定依赖传统 OCR pipeline。多模态大模型进一步把文档理解、图表分析、表格问答整合到通用视觉语言能力中。

</details>

<details>
<summary><strong>11.3 Upstream & Downstream / 上下游定位</strong></summary>

OCR 与文档理解通常是“视觉内容进入文本系统”的接口层，也是多模态大模型、办公自动化和 GUI Agent 的重要前置能力。

```text
上游输入：扫描文档、票据、表格、网页截图、PPT/PDF 页面、自然场景文字、屏幕 UI
本章输出：文本框、识别文本、阅读顺序、版面块、表格结构、key-value 字段、文档问答结果
下游模块：信息抽取、RAG / 文档问答、搜索索引、票据审核、办公自动化、GUI / Web Agent、机器人读屏
核心难点：文字识别、版面结构、跨区域字段关系和图表/表格语义必须同时建模
```

因此，文档理解论文不能只看 OCR 字符准确率，还要看它能否保留结构信息，并把结果稳定交给后续检索、推理或执行模块。

</details>

<details>
<summary><strong>11.4 Representative Works / 代表性工作速览</strong></summary>

| 年份 / Year | 方法 / Work | 位置 / Position | 为什么重要 / Why it matters |
|---:|---|---|---|
| 2015 | CRNN / CTC | 端到端文字识别 | 不再依赖字符级切分，把文本行识别建模为序列学习问题 |
| 2017 | EAST | 场景文字检测 | 用高效全卷积检测器直接预测文本区域几何 |
| 2019 | CRAFT | 任意形状文本检测 | 用字符区域和 affinity 建模复杂文本实例 |
| 2021 | TrOCR | Transformer OCR | 把 OCR 统一为视觉编码器到文本解码器的序列生成 |
| 2019–2022 | LayoutLM / LayoutLMv2 / LayoutLMv3 | 版面感知预训练 | 联合文本、位置和视觉信息建模文档结构 |
| 2021 | PubTables-1M / Table Transformer | 表格理解 | 面向表格检测、结构识别和功能区域分析的数据与模型路线 |
| 2021 | Donut | OCR-free 文档理解 | 直接从文档图像生成结构化结果，弱化显式 OCR 依赖 |
| 2022 | Pix2Struct | 截图/网页/图表理解 | 用 screenshot parsing 预训练统一视觉到结构化文本的建模接口 |

</details>

<details>
<summary><strong>11.5 Paper Positioning / 论文归位指引</strong></summary>

读 OCR 或文档理解论文时，先问：

```text
1. 它处理的是场景文字、扫描文档、表格、图表，还是多页 PDF？
2. 它输出字符串、文本框、版面结构，还是结构化 JSON？
3. 它依赖 OCR pipeline，还是端到端图像到文本？
4. 它解决的是弯曲文字、低清晰度、多语言、复杂版面，还是长文档推理？
5. 它服务自动驾驶、机器人读屏、办公自动化，还是多模态大模型？
```

</details>

<details>
<summary><strong>11.6 Paper Cards / 核心论文卡片</strong></summary>

> 本节集中放置本章代表论文入口。正文和代表论文表格中的方法名优先跳转到这里，外部 Paper / Code / Project 链接只在论文卡片中出现。

<a id="paper-11-crnn-ctc"></a>

#### CRNN / CTC

- **Title / 标题**：An End-to-End Trainable Neural Network for Image-based Sequence Recognition and Its Application to Scene Text Recognition
- **Year / 年份**：2015
- **Core Contribution / 核心贡献**：用 CNN 提取视觉特征、RNN 建模序列，并通过 CTC 在无字符级切分标注下训练端到端文本行识别模型。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1507.05717)
<a id="paper-11-east"></a>

#### EAST

- **Title / 标题**：EAST: An Efficient and Accurate Scene Text Detector
- **Year / 年份**：2017
- **Core Contribution / 核心贡献**：用单阶段全卷积网络直接回归文本区域几何，简化候选框与字符级流程，提高场景文字检测效率。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1704.03155)
<a id="paper-11-craft"></a>

#### CRAFT

- **Title / 标题**：Character Region Awareness for Text Detection
- **Year / 年份**：2019
- **Core Contribution / 核心贡献**：通过字符区域和字符间 affinity 建模文本实例，使模型能从局部字符线索恢复弯曲或任意形状文本。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1904.01941)
<a id="paper-11-trocr"></a>

#### TrOCR

- **Title / 标题**：TrOCR: Transformer-based Optical Character Recognition with Pre-trained Models
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：将 OCR 统一为视觉编码器到文本解码器的 Transformer 序列生成任务，并借助预训练提升印刷体和手写体识别。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2109.10282)
<a id="paper-11-layoutlm"></a>

#### LayoutLM / LayoutLMv2 / LayoutLMv3

- **Title / 标题**：Layout-aware Document Pre-training
- **Year / 年份**：2019–2022
- **Core Contribution / 核心贡献**：把文本 token、二维版面坐标和视觉信息联合预训练，使模型能理解字段关系、阅读顺序和文档版面结构。
- **Links / 链接**：[LayoutLM](https://arxiv.org/abs/1912.13318) / [LayoutLMv2](https://arxiv.org/abs/2012.14740) / [LayoutLMv3](https://arxiv.org/abs/2204.08387)
<a id="paper-11-table-transformer"></a>

#### Table Transformer

- **Title / 标题**：PubTables-1M: Towards Comprehensive Table Extraction From Unstructured Documents
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：提出 PubTables-1M 数据集，并用 DETR-style Table Transformer 处理表格检测、结构识别和功能区域分析。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2110.00061)
<a id="paper-11-donut"></a>

#### Donut

- **Title / 标题**：OCR-free Document Understanding Transformer
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：用视觉编码器和文本解码器直接从文档图像生成结构化结果，证明 OCR-free 文档理解在票据、表单和问答中可行。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2111.15664)
<a id="paper-11-pix2struct"></a>

#### Pix2Struct

- **Title / 标题**：Screenshot Parsing as Pretraining for Visual Language Understanding
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：将 screenshot parsing 作为预训练任务，把网页、表格、图表和文档图像统一转成结构化文本，增强视觉语言理解。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2210.03347)
</details>

### 12. Multimodal Understanding / 多模态理解

<details open>
<summary><strong>12.0 Quick Overview / 一页速览</strong></summary>

```text
Multimodal Understanding / 多模态理解

├── 任务本质
│   ├── 把图像、视频、文本、语音、文档、动作等不同模态映射到共同语义空间
│   └── 让模型能回答、描述、定位、推理、检索、操作
│
├── 典型输入
│   ├── image + text
│   ├── video + text
│   ├── document + question
│   ├── GUI screenshot + instruction
│   └── robot observation + language instruction
│
├── 典型输出
│   ├── caption / 描述
│   ├── answer / 回答
│   ├── bounding box / 定位框
│   ├── mask / 分割区域
│   ├── reasoning trace / 推理过程
│   ├── tool call / 工具调用
│   └── action / 动作
│
└── 方法演化
    ├── 手工融合与双流模型
    ├── 图文预训练：ViLBERT / LXMERT / UNITER / OSCAR / VinVL
    ├── 对比式图文对齐：CLIP / ALIGN / SigLIP
    ├── 生成式视觉语言模型：BLIP / BLIP-2 / Flamingo
    ├── 指令微调 MLLM：MiniGPT-4 / LLaVA / InstructBLIP
    ├── 多场景统一 MLLM：LLaVA-OneVision / Qwen2.5-VL / InternVL3
    └── Agentic MLLM：视觉定位、GUI 操作、工具调用、长期任务
```

</details>

<details>
<summary><strong>12.1 Basic Definition & Task Variants / 核心定义与任务变体</strong></summary>

**Multimodal Understanding / 多模态理解** 不是简单地“把图像和文字拼到一起”。它真正要解决的是：

```text
视觉负责提供世界状态，语言负责提供任务、概念、指令、推理结构。
多模态模型要把二者对齐，使系统能在同一个语义空间里理解图像、文本和任务。
```

典型任务包括：

```text
Image Captioning / 图像描述：给图像生成一句话。
Visual Question Answering / 视觉问答：根据图像回答问题。
Image-Text Retrieval / 图文检索：用文字找图，或用图找文字。
Visual Grounding / 视觉定位：把语言短语定位到图像区域。
Document VQA / 文档问答：读文档、表格、票据、PDF。
Video Question Answering / 视频问答：理解长时间动作、事件和因果关系。
GUI Agent / 图形界面智能体：根据屏幕和指令点击、输入、操作软件。
Embodied Multimodal Agent / 具身多模态智能体：把视觉、语言与动作连接起来。
```

新手需要特别注意：

> 多模态理解不是一个单独任务，而是一组“视觉语义接口”。它把分类、检测、分割、OCR、视频理解、导航、机器人控制连接到语言空间里。

</details>

<details>
<summary><strong>12.2 Method Evolution / 方法演化主线</strong></summary>

<details open>
<summary><strong>12.2.1 Early VLP / 早期视觉语言预训练</strong></summary>

早期视觉语言模型通常围绕 VQA、captioning、image-text matching 等任务构建。代表方法包括 ViLBERT、LXMERT、UNITER、OSCAR、VinVL 等。

它们的共同特点是：

```text
1. 通常依赖目标检测器提取 region features；
2. 把图像区域和文本 token 送入跨模态 Transformer；
3. 通过匹配、掩码预测、问答等任务学习图文关系。
```

这类方法的重要意义在于：它们第一次系统地把视觉对象、文本词语、句子语义放进同一个预训练框架中。

但它们的问题也很明显：

```text
依赖检测器 → 视觉输入不够端到端；
任务碎片化 → 每个任务需要专门 head；
开放类别能力弱 → 很难泛化到训练集之外的概念；
生成能力弱 → 主要做判别式理解。
```

</details>

<details>
<summary><strong>12.2.2 CLIP-style Contrastive Alignment / CLIP 式图文对齐</strong></summary>

CLIP 是多模态理解中的分水岭。它的核心不是复杂结构，而是把大规模图文对通过对比学习对齐：

```text
图像编码器输出 image embedding
文本编码器输出 text embedding
正确图文对拉近，不匹配图文对拉远
```

CLIP 的意义在于：

```text
1. 让视觉模型拥有开放词汇分类能力；
2. 让图像可以用自然语言标签来检索和识别；
3. 成为开放词汇检测、开放词汇分割、图像生成、图像编辑的重要语义底座。
```

后续 ALIGN、LiT、SigLIP 等方法继续沿着这条路线改进数据规模、训练目标、损失函数和视觉编码器。

新手可以这样理解：

> CLIP 不直接解决检测或分割，但它给很多视觉任务提供了“语言语义坐标系”。

</details>

<details>
<summary><strong>12.2.3 Generative VLM / 生成式视觉语言模型</strong></summary>

BLIP、BLIP-2、Flamingo 等方法把多模态模型从“对齐”进一步推向“生成”。

其中 BLIP 强调统一理解与生成；BLIP-2 的关键是用轻量 Querying Transformer 把冻结视觉编码器和冻结大语言模型连接起来；Flamingo 则探索了如何让大语言模型通过交叉注意力接收视觉输入，并具备少样本多模态能力。

这一阶段的核心变化是：

```text
从：图像和文本是否匹配？
到：给我图像，我能不能生成回答、解释和推理？
```

这为后续 LLaVA、MiniGPT-4、InstructBLIP 等 MLLM 铺平了道路。

</details>

<details>
<summary><strong>12.2.4 MLLM Era / 多模态大模型时代</strong></summary>

MLLM 通常采用三段式结构：

```text
Vision Encoder / 视觉编码器
→ Connector / 投影层或跨模态连接器
→ LLM / 大语言模型
```

这里还有一个容易被新手忽略的关键问题：**视觉 Token 压缩 / Visual Token Compression**。图像尤其是高分辨率图像会产生大量视觉 token，如果全部送入 LLM，计算成本和上下文长度都会迅速膨胀。因此许多 MLLM 会通过 query token、resampler、patch merging、动态切图、区域裁剪或自适应分辨率等方式，把“看得清楚”和“算得动”之间做平衡。

```text
高分辨率图像
→ patch / tile / region tokens
→ token compression / resampling
→ LLM 可处理的视觉 token 序列
```

早期代表包括 MiniGPT-4、LLaVA、InstructBLIP。它们证明：只要把视觉特征对齐到大语言模型的输入空间，再进行图文指令微调，就可以得到一个能看图聊天、回答问题、解释场景的模型。

之后的发展重点转向：

```text
更强的视觉感知：高分辨率、多图、多目标、细粒度定位；
更强的视频理解：长视频、多帧推理、事件因果；
更强的文档能力：OCR、表格、图表、PDF；
更强的工具能力：调用检测器、分割器、浏览器、代码工具；
更强的 Agent 能力：GUI 操作、网页导航、任务执行。
```

例如 LLaVA-OneVision 强调单图、多图、视频三种视觉场景的统一迁移；Qwen2.5-VL 技术报告强调视觉识别、精确定位、文档解析、长视频理解和视觉 Agent 能力；InternVL3 则强调原生多模态预训练和更强的多模态推理能力。

</details>

<details>
<summary><strong>12.2.5 From MLLM to Agent / 从多模态大模型到视觉智能体</strong></summary>

当 MLLM 能够理解图像和语言之后，下一步自然是：

```text
它能不能根据屏幕内容执行操作？
它能不能调用工具完成任务？
它能不能把视觉理解转化成行动计划？
```

这就进入了视觉 Agent 阶段。典型方向包括：

```text
GUI Agent / 图形界面智能体：看屏幕、理解按钮、点击与输入；
Web Agent / 网页智能体：浏览网页、检索信息、执行网页任务；
Tool-using MLLM / 工具调用模型：调用 OCR、检测器、分割器、代码解释器；
Embodied Agent / 具身智能体：把视觉语言理解连接到机器人动作。
```

这一阶段的关键瓶颈不是“模型是否能描述图像”，而是：

```text
定位是否精确？
动作是否可执行？
错误能否恢复？
长程任务中是否保持目标？
是否能避免幻觉和危险操作？
```

</details>

</details>

<details>
<summary><strong>12.3 Upstream & Downstream / 上下游定位</strong></summary>

多模态理解把视觉内容和语言语义对齐，是开放世界视觉系统的语义接口。

```text
上游输入：图像、视频、文本、OCR 结果、区域/对象特征、图文对数据
本章输出：图文匹配、caption、VQA 答案、视觉推理结果、跨模态 embedding
下游模块：开放词汇检测/分割、文档问答、视觉搜索、机器人语言理解、视觉智能体
系统价值：让视觉结果可以被自然语言查询、解释和组合
```

</details>

<details>
<summary><strong>12.4 Representative Works / 代表性工作速览</strong></summary>

| 年份 / Year | 方法 / Work | 位置 / Position | 为什么重要 / Why it matters |
|---:|---|---|---|
| 2019–2020 | ViLBERT / LXMERT / UNITER | 早期视觉语言预训练 | 代表 region feature + cross-modal Transformer 路线 |
| 2020–2021 | OSCAR / VinVL | 对象标签增强 VLP | 强调 object tags 对图文理解的重要性 |
| 2021 | CLIP | 图文对比学习 | 奠定开放词汇视觉语义基础 |
| 2021 | ALIGN | 大规模图文对齐 | 证明噪声图文对在超大规模下可训练强图文模型 |
| 2022 | BLIP | 统一理解与生成 | 连接 caption、VQA、retrieval 等任务 |
| 2023 | BLIP-2 | 冻结视觉模型 + 冻结 LLM | 用 Q-Former 高效连接视觉与语言大模型 |
| 2022 | Flamingo | few-shot VLM | 探索大语言模型接收视觉上下文的少样本能力 |
| 2023 | LLaVA | 指令微调 MLLM | 让视觉语言模型进入“看图对话”阶段 |
| 2024 | LLaVA-OneVision | 图像、多图、视频统一 | 强调视觉任务跨场景迁移 |
| 2025 | Qwen2.5-VL | 强视觉定位、文档、长视频、Agent | 代表近年开源 MLLM 的综合能力路线 |
| 2025 | InternVL3 | 原生多模态预训练 | 强调联合学习多模态和语言能力 |

</details>

<details>
<summary><strong>12.5 Paper Positioning / 论文归位指引</strong></summary>

看到一篇多模态论文，先不要只问“它是不是 MLLM”。更好的定位方式是：

```text
1. 它的输入是什么？图像+文本，视频+文本，文档+问题，还是屏幕+指令？
2. 它的输出是什么？文本回答、框、mask、动作、工具调用，还是多轮交互？
3. 它改的是视觉编码器、连接器、LLM、训练数据、指令微调，还是评估方式？
4. 它解决什么痛点？定位不准、长视频弱、OCR 弱、幻觉、工具不会用、动作不可执行？
5. 它服务哪个下游？开放词汇检测、文档理解、视觉导航、自动驾驶、机器人控制？
```

例如：

```text
Qwen2.5-VL
主归属：MLLM / 多模态大模型
交叉归属：视觉定位、文档理解、长视频理解、视觉 Agent
不是：普通图像分类模型

LLaVA-OneVision
主归属：统一视觉语言模型
交叉归属：单图、多图、视频理解
不是：只面向静态图像问答的 VQA 模型
```

</details>

<details>
<summary><strong>12.6 Paper Cards / 核心论文卡片</strong></summary>

> 本节集中放置本章代表论文入口。正文和代表论文表格中的方法名优先跳转到这里，外部 Paper / Code / Project 链接只在论文卡片中出现。

<a id="paper-12-vilbert-lxmert-uniter"></a>

#### ViLBERT / LXMERT / UNITER

- **Title / 标题**：ViLBERT: Pretraining Task-Agnostic Visiolinguistic Representations for Vision-and-Language Tasks / LXMERT: Learning Cross-Modality Encoder Representations from Transformers / UNITER: UNiversal Image-TExt Representation Learning
- **Year / 年份**：2019–2020
- **Core Contribution / 核心贡献**：代表 region feature + cross-modal Transformer 路线。
- **Links / 链接**：[ViLBERT](https://arxiv.org/abs/1908.02265) / [LXMERT](https://arxiv.org/abs/1908.07490) / [UNITER](https://arxiv.org/abs/1909.11740)
<a id="paper-12-oscar-vinvl"></a>

#### OSCAR / VinVL

- **Title / 标题**：Oscar: Object-Semantics Aligned Pre-training for Vision-Language Tasks / VinVL: Revisiting Visual Representations in Vision-Language Models
- **Year / 年份**：2020–2021
- **Core Contribution / 核心贡献**：强调 object tags 对图文理解的重要性。
- **Links / 链接**：[OSCAR](https://arxiv.org/abs/2004.06165) / [VinVL](https://arxiv.org/abs/2101.00529)
<a id="paper-12-clip"></a>

#### CLIP

- **Title / 标题**：Learning Transferable Visual Models From Natural Language Supervision
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：奠定开放词汇视觉语义基础。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2103.00020)
<a id="paper-12-align"></a>

#### ALIGN

- **Title / 标题**：Scaling Up Visual and Vision-Language Representation Learning With Noisy Text Supervision
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：证明噪声图文对在超大规模下可训练强图文模型。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2102.05918)
<a id="paper-12-blip"></a>

#### BLIP

- **Title / 标题**：BLIP: Bootstrapping Language-Image Pre-training for Unified Vision-Language Understanding and Generation
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：连接 caption、VQA、retrieval 等任务。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2201.12086)
<a id="paper-12-blip-2"></a>

#### BLIP-2

- **Title / 标题**：BLIP-2: Bootstrapping Language-Image Pre-training with Frozen Image Encoders and Large Language Models
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：用 Q-Former 高效连接视觉与语言大模型。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2301.12597)
<a id="paper-12-flamingo"></a>

#### Flamingo

- **Title / 标题**：Flamingo: a Visual Language Model for Few-Shot Learning
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：探索大语言模型接收视觉上下文的少样本能力。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2204.14198)
<a id="paper-12-llava"></a>

#### LLaVA

- **Title / 标题**：Visual Instruction Tuning
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：让视觉语言模型进入“看图对话”阶段。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2304.08485)
<a id="paper-12-llava-onevision"></a>

#### LLaVA-OneVision

- **Title / 标题**：LLaVA-OneVision: Easy Visual Task Transfer
- **Year / 年份**：2024
- **Core Contribution / 核心贡献**：强调视觉任务跨场景迁移。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2408.03326)
<a id="paper-12-qwen2-5-vl"></a>

#### Qwen2.5-VL

- **Title / 标题**：Qwen2.5-VL Technical Report
- **Year / 年份**：2025
- **Core Contribution / 核心贡献**：代表近年开源 MLLM 的综合能力路线。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2502.13923)
<a id="paper-12-internvl3"></a>

#### InternVL3

- **Title / 标题**：InternVL3: Exploring Advanced Training and Test-Time Recipes for Open-Source Multimodal Models
- **Year / 年份**：2025
- **Core Contribution / 核心贡献**：强调联合学习多模态和语言能力。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2504.10479)
</details>

### 13. Open-Vocabulary Perception / 开放世界感知

<details open>
<summary><strong>13.0 Quick Overview / 一页速览</strong></summary>

```text
Visual-Semantic Guidance & Open-Vocabulary Perception / 视觉语义引导与开放词汇感知

├── 核心问题
│   ├── 传统视觉任务只能识别训练集里固定类别
│   ├── 现实世界类别开放、语言描述灵活、任务目标不断变化
│   └── 需要用语言、文本、提示或语义知识引导视觉感知
│
├── 主要方向
│   ├── Visual Grounding / 视觉定位
│   ├── Referring Detection / 指代表达检测
│   ├── Referring Segmentation / 指代表达分割
│   ├── Open-Vocabulary Detection / 开放词汇检测
│   ├── Open-Vocabulary Segmentation / 开放词汇分割
│   ├── Grounded-SAM / 语言定位 + 可提示分割
│   ├── Semantic-guided Low-level Vision / 语义引导低层视觉
│   └── Embodied Semantic Guidance / 具身语义引导
│
└── 技术主线
    CLIP 语义空间
    → GLIP 统一检测与短语定位
    → OWL-ViT / OWLv2 开放词汇检测
    → Grounding DINO 开放集定位
    → SAM / SAM 2 可提示分割
    → Grounded-SAM 组合式开放世界感知
    → MLLM / Agent 解释、定位、分割、行动一体化
```

</details>

<details>
<summary><strong>13.1 Basic Definition & Task Variants / 核心定义与任务变体</strong></summary>

**Visual-Semantic Guidance / 视觉语义引导** 指的是用语言、文本标签、语义嵌入、知识图谱、任务指令或可供性概念来指导视觉模型。

它和普通视觉任务的区别是：

```text
普通检测：检测训练集中的 person / car / dog。
开放词汇检测：给一句 “red fire extinguisher near the door”，模型要找出对应物体。
普通分割：分割固定类别 road / sky / person。
指代表达分割：根据 “the small cup on the left of the laptop” 分割目标。
普通图像增强：让图像更清楚。
语义引导增强：为了让下游检测、识别、导航更好而增强。
```

因此，它不是某一个单独任务，而是一条横向主线：

> 让视觉系统从“固定标签识别”升级为“根据语言和任务目标动态感知”。

</details>

<details>
<summary><strong>13.2 Method Evolution / 方法演化主线</strong></summary>

<details open>
<summary><strong>13.2.1 Visual Grounding / 视觉定位</strong></summary>

视觉定位的目标是把语言短语映射到图像区域。典型形式包括：

```text
Phrase Grounding / 短语定位：定位句子里的名词短语。
Referring Expression Comprehension / 指代表达理解：根据描述找到目标框。
Referring Expression Segmentation / 指代表达分割：根据描述输出目标 mask。
```

这类任务很适合新手理解“语言如何进入视觉”：

```text
不是让模型回答图片里有什么，
而是让模型把语言中的具体对象落到图像坐标中。
```

它是开放词汇检测、开放词汇分割、视觉 Agent、具身操作的重要基础。

</details>

<details>
<summary><strong>13.2.2 Open-Vocabulary Detection / 开放词汇检测</strong></summary>

传统检测器只能检测训练集类别，例如 COCO 的 80 类。开放词汇检测则希望模型根据任意文本类别检测目标。

这条主线可以这样理解：

```text
Faster R-CNN / YOLO / DETR：固定类别检测
CLIP：获得开放文本语义空间
GLIP：统一 object detection 与 phrase grounding
OWL-ViT / OWLv2：把 image-text pretraining 转化为开放词汇检测
Grounding DINO：把 DINO 检测器与 grounded pre-training 结合
Grounding DINO 1.5：进一步追求更强泛化与边缘部署
DINO-X：向 object-centric open-world perception 继续扩展
```

这条线的本质不是“检测器用了文本”，而是：

> 检测类别不再由训练集 label space 决定，而是由语言提示决定。

</details>

<details>
<summary><strong>13.2.3 Open-Vocabulary Segmentation / 开放词汇分割</strong></summary>

开放词汇分割比开放词汇检测更难，因为它不仅要知道“在哪里有目标”，还要输出像素级区域。

代表性路线包括：

```text
CLIP-based dense prediction：把 CLIP 语义迁移到像素级任务。
MaskCLIP / DenseCLIP：用 CLIP 的视觉语言空间做 dense prediction。
CLIPSeg：根据文本提示产生分割 mask。
X-Decoder：统一 pixel、image、language 的 generalized decoding。
SEEM：用多种 prompt 做通用交互式分割。
Grounded-SAM：用 Grounding DINO 找框，用 SAM 输出 mask。
```

这里要注意：SAM 本身不是开放词汇语义分割模型。SAM 强在“根据点、框、mask 等 prompt 生成高质量分割区域”，但它不知道这个区域的语义类别。Grounded-SAM 的意义是把语言定位和可提示分割组合起来：

```text
文本提示 → Grounding DINO 找目标框 → SAM 输出精细 mask
```

这就是现代视觉系统常见的“组合式基础模型”思路。

</details>

<details>
<summary><strong>13.2.4 Semantic-guided Low-level Vision / 语义引导低层视觉</strong></summary>

低层视觉传统上关心图像是否清晰，例如去噪、去雨、去雾、增强、融合、超分。但是很多应用里，图像变清楚不是最终目的，下游任务才是最终目的。

因此出现了语义引导低层视觉：

```text
Semantic-guided Restoration / 语义引导恢复
Task-driven Enhancement / 面向检测、分割、识别的增强
Semantic-guided Fusion / 语义引导融合
Text-guided Image Fusion / 文本引导红外-可见光融合
Detection-aware Super-resolution / 面向检测的小目标超分
```

它和普通图像恢复的区别是：

```text
普通恢复：PSNR / SSIM 更高。
任务驱动恢复：检测 mAP、分割 mIoU、识别准确率更高。
语义引导恢复：增强过程知道哪些区域和语义更重要。
```

所以在最终地图中，它应该同时出现在：

```text
低层视觉 / 图像恢复与融合
多模态理解 / 语义引导
自动驾驶 / 恶劣天气感知
机器人 / 弱光与复杂环境感知
```

</details>

<details>
<summary><strong>13.2.5 Embodied Semantic Guidance / 具身语义引导</strong></summary>

当语义引导进入机器人和自动驾驶，问题就不只是“找出图像里的物体”，而是：

```text
哪个物体和任务有关？
它能不能被抓？
它是否可通行？
它和指令中的目标是什么关系？
下一步该朝哪里走？
```

典型方向包括：

```text
Object-goal Navigation / 目标物导航
Vision-Language Navigation / 视觉语言导航
Embodied Question Answering / 具身问答
Affordance-guided Manipulation / 可供性引导操作
Language-conditioned Policy / 语言条件策略
```

这里的“语义”不再只是类别名，而是任务相关意义：

```text
cup：不只是一个物体类别，而是可以拿、可以装水、可能在桌上、和“倒水”任务相关。
chair：不只是一个类别，而是可坐、可移动、可能阻挡路径。
red light：不只是红色灯，而是车辆必须停止的交通规则信号。
```

</details>

</details>

<details>
<summary><strong>13.3 Upstream & Downstream / 上下游定位</strong></summary>

开放世界感知位于传统闭集感知和真实开放场景之间。

```text
上游输入：图像/视频、文本类别名、视觉语言特征、基础检测/分割模型、少量标注或伪标签
本章输出：开放词汇检测框、开放词汇 mask、未知类发现、文本条件 grounding 结果
下游模块：自动标注、数据引擎、机器人语言指令感知、长尾类别识别、开放世界自动驾驶
系统价值：把固定类别感知扩展到可由语言指定、可发现未知对象的感知接口
```

</details>

<details>
<summary><strong>13.4 Representative Works / 代表性工作速览</strong></summary>

| 年份 / Year | 方法 / Work | 位置 / Position | 为什么重要 / Why it matters |
|---:|---|---|---|
| 2021 | CLIP | 开放语义空间 | 给视觉任务提供语言语义坐标系 |
| 2021 | GLIP | 检测 + 短语定位统一预训练 | 把 object detection 和 phrase grounding 统一起来 |
| 2022 | OWL-ViT | 开放词汇检测 | 把图文预训练模型转化为开放词汇 detector |
| 2023 | Grounding DINO | 开放集检测与语言定位 | 用 DINO 检测器结合 grounded pre-training，支持类别名和指代表达 |
| 2023 | Grounding DINO 1.5 | 强泛化与边缘开放检测 | 将开放词汇检测向高性能和高效率推进 |
| 2021 | CLIPSeg | 文本提示分割 | 早期文本驱动分割代表 |
| 2022 | X-Decoder | pixel-image-language 统一解码 | 支持通用分割、开放词汇分割和视觉语言任务 |
| 2023 | SEEM | 多提示通用分割 | 支持点、框、涂鸦、mask、文本等多种 prompt |
| 2023–2024 | Grounded-SAM / Grounded-SAM 2 | 组合式开放世界感知 | Grounding DINO + SAM / SAM 2，连接语言定位与精细分割 |
| 2023 | LISA / reasoning segmentation 类方法 | 推理式分割 | 让 MLLM 通过语言推理输出目标区域 |

</details>

<details>
<summary><strong>13.5 Paper Positioning / 论文归位指引</strong></summary>

看到一篇视觉语义相关论文，可以这样判断：

```text
1. 它是在做 grounding、open-vocabulary detection，还是 open-vocabulary segmentation？
2. 它输入的是类别名、短语、自然语言描述，还是多轮对话？
3. 它输出的是框、mask、文本、动作，还是工具调用？
4. 它依赖 CLIP / Grounding DINO / SAM / MLLM 中的哪一个作为底座？
5. 它是端到端模型，还是组合式系统？
6. 它解决的是开放类别、细粒度定位、推理分割、下游任务提升，还是边缘部署？
```

例子：

```text
Grounding DINO
主归属：Open-Vocabulary Detection / Visual Grounding
交叉归属：Object Detection、多模态理解、Grounded-SAM 系统
核心贡献：把语言引入 DINO 检测器，实现开放集目标定位

X-Decoder
主归属：Open-Vocabulary Segmentation / Generalist Vision-Language Decoder
交叉归属：Image Segmentation、多模态理解、统一视觉系统
核心贡献：统一 pixel-level 和 token-level 输出

SEEM
主归属：Promptable Universal Segmentation
交叉归属：Image Segmentation、Open-vocabulary Segmentation、Interactive Perception
核心贡献：多种 prompt 形式统一到一个交互式分割接口
```

</details>

<details>
<summary><strong>13.6 Paper Cards / 核心论文卡片</strong></summary>

> 本节集中放置本章代表论文入口。正文和代表论文表格中的方法名优先跳转到这里，外部 Paper / Code / Project 链接只在论文卡片中出现。

<a id="paper-13-clip"></a>

#### CLIP

- **Title / 标题**：Learning Transferable Visual Models From Natural Language Supervision
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：给视觉任务提供语言语义坐标系。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2103.00020)
<a id="paper-13-glip"></a>

#### GLIP

- **Title / 标题**：Grounded Language-Image Pre-training
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：把 object detection 和 phrase grounding 统一起来。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2112.03857)
<a id="paper-13-owl-vit"></a>

#### OWL-ViT

- **Title / 标题**：Simple Open-Vocabulary Object Detection with Vision Transformers
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：把图文预训练模型转化为开放词汇 detector。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2205.06230)
<a id="paper-13-grounding-dino"></a>

#### Grounding DINO

- **Title / 标题**：Grounding DINO: Marrying DINO with Grounded Pre-Training for Open-Set Object Detection
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：用 DINO 检测器结合 grounded pre-training，支持类别名和指代表达。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2303.05499)
<a id="paper-13-grounding-dino-1-5"></a>

#### Grounding DINO 1.5

- **Title / 标题**：Grounding DINO 1.5: Advance the Edge of Open-Set Object Detection
- **Year / 年份**：2024
- **Core Contribution / 核心贡献**：将开放词汇检测向高性能和高效率推进。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2405.10300)
<a id="paper-13-clipseg"></a>

#### CLIPSeg

- **Title / 标题**：Image Segmentation Using Text and Image Prompts
- **Year / 年份**：2021/2022
- **Core Contribution / 核心贡献**：早期文本驱动分割代表。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2112.10003)
<a id="paper-13-x-decoder"></a>

#### X-Decoder

- **Title / 标题**：Generalized Decoding for Pixel, Image, and Language
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：支持通用分割、开放词汇分割和视觉语言任务。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2212.11270)
<a id="paper-13-seem"></a>

#### SEEM

- **Title / 标题**：Segment Everything Everywhere All at Once
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：支持点、框、涂鸦、mask、文本等多种 prompt。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2304.06718)
<a id="paper-13-grounded-sam-grounded-sam-2"></a>

#### Grounded-SAM / Grounded-SAM 2

- **Title / 标题**：Grounded-SAM / Grounded-SAM 2: Grounding DINO + Segment Anything for grounded segmentation
- **Year / 年份**：2023–2024
- **Core Contribution / 核心贡献**：Grounding DINO + SAM / SAM 2，连接语言定位与精细分割。
- **Links / 链接**：[Grounded-SAM](https://github.com/IDEA-Research/Grounded-Segment-Anything) / [Grounded-SAM 2](https://github.com/IDEA-Research/Grounded-SAM-2)
<a id="paper-13-lisa-reasoning-segmentation-类方法"></a>

#### LISA / Reasoning Segmentation 类方法

- **Title / 标题**：LISA: Reasoning Segmentation via Large Language Model
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：让 MLLM 通过语言推理输出目标区域。
- **Links / 链接**：[LISA](https://arxiv.org/abs/2308.00692)
</details>

### 14. VFM, MLLM & Agents / 视觉大模型与智能体

<details open>
<summary><strong>14.0 Quick Overview / 一页速览</strong></summary>

```text
Vision Foundation Models, MLLM & Visual Agents / 视觉基础模型、多模态大模型与视觉智能体

├── Vision Foundation Models / 视觉基础模型
│   ├── 表征型：MAE / DINOv2 / CLIP / SigLIP
│   ├── 感知型：SAM / SAM 2 / Grounding DINO / DINO-X
│   ├── 生成型：Stable Diffusion / ControlNet / video generation models
│   └── 三维型：DUSt3R / VGGT / NeRF / 3DGS 相关基础表示
│
├── MLLM / 多模态大模型
│   ├── 看图对话
│   ├── 文档理解
│   ├── 长视频理解
│   ├── 视觉定位
│   └── 多轮推理
│
├── Visual Agent / 视觉智能体
│   ├── GUI Agent：看屏幕、点击、输入
│   ├── Tool-using Agent：调用 OCR、检测、分割、搜索、代码工具
│   ├── Embodied Agent：连接机器人动作
│   └── Driving Agent：连接驾驶决策和规划
│
└── 核心瓶颈
    ├── spatial grounding / 空间定位
    ├── hallucination / 幻觉
    ├── long-horizon consistency / 长程一致性
    ├── verification / 可验证性
    └── safety / 安全性
```

</details>

<details>
<summary><strong>14.1 Basic Definition & Task Variants / 核心定义与任务变体</strong></summary>

#### What Is a Vision Foundation Model? / 什么是视觉基础模型？

“基础模型”这个词容易被滥用。对于视觉领域，更实用的定义是：

> 一个模型如果能通过大规模预训练学到通用能力，并能迁移到许多下游视觉任务，就可以被视作视觉基础模型。

它不一定必须是语言模型，也不一定必须会聊天。按照能力可以分成几类：

```text
Representation Foundation Model / 表征基础模型
例：MAE、DINOv2、CLIP、SigLIP
作用：提供通用视觉特征。

Promptable Perception Foundation Model / 可提示感知基础模型
例：SAM、SAM 2、Grounding DINO
作用：通过 prompt 完成分割、定位、跟踪。

Generative Foundation Model / 生成式基础模型
例：Stable Diffusion、ControlNet、视频生成模型
作用：生成、编辑、补全视觉内容。

3D / Spatial Foundation Model / 三维空间基础模型
例：DUSt3R、VGGT、NeRF/3DGS 相关表示
作用：从图像恢复三维结构、相机、点云和可渲染场景。

Multimodal Foundation Model / 多模态基础模型
例：LLaVA、Qwen2.5-VL、InternVL、Gemini 系列
作用：连接图像、视频、文本、文档、工具和任务。
```

#### 14.1.1 Common Misunderstandings / 常见误区

```text
误区 1：会看图聊天 = 视觉基础模型。
纠正：看图聊天只是 MLLM 的一种能力，视觉基础模型还包括表征、分割、生成、三维等类型。

误区 2：SAM = 开放词汇分割。
纠正：SAM 擅长 promptable mask generation，但本身不提供语义类别。Grounded-SAM 才把语言定位和 SAM 组合起来。

误区 3：MLLM 能描述图像，就能可靠做自动驾驶或机器人。
纠正：描述能力不等于空间定位、物理执行和闭环安全能力。

误区 4：Agent 就是多轮对话。
纠正：Agent 的关键是目标驱动、工具调用、环境交互和结果反馈。
```

</details>

<details>
<summary><strong>14.2 Method Evolution / 方法演化主线</strong></summary>

#### From Model to Agent / 从模型到智能体

模型和智能体的区别在于：

```text
模型：给输入，产生输出。
智能体：根据目标，观察环境，调用工具，执行动作，检查结果，继续迭代。
```

视觉智能体通常需要四种能力：

```text
Perception / 感知：看懂图像、屏幕、视频或现实场景。
Grounding / 定位：知道文本中的目标对应图像中的哪个位置。
Reasoning / 推理：分解任务、选择步骤、解释因果。
Action / 行动：点击、输入、调用工具、移动、操作物体。
```

因此，一个 GUI Agent 或机器人 Agent 不只是“有视觉输入的聊天模型”。它必须能把视觉理解转成可执行的动作。

#### Typical Visual Agent Forms / 典型视觉智能体形态

```text
1. GUI Agent / 图形界面智能体
输入：屏幕截图 + 用户指令
输出：点击位置、键盘输入、应用操作
核心难点：小图标识别、OCR、坐标定位、多步任务、错误恢复

2. Web Agent / 网页智能体
输入：网页截图、DOM、搜索结果、用户目标
输出：浏览、点击、填写表单、综合答案
核心难点：网页结构变化、误点击、信息可信度、长任务规划

3. Tool-using Visual Agent / 工具型视觉智能体
输入：图像/视频/文档 + 问题
输出：调用 OCR、检测器、分割器、Python、搜索工具后的综合答案
核心难点：什么时候调用什么工具，如何验证工具结果

4. Embodied Visual Agent / 具身视觉智能体
输入：机器人相机、语言指令、本体状态
输出：导航、抓取、放置、操作动作
核心难点：物理可执行性、接触、长程任务、安全

5. Driving Visual Agent / 驾驶视觉智能体
输入：多摄像头、地图、交通规则、语言提示
输出：场景解释、风险判断、行为决策、规划辅助
核心难点：空间推理、实时性、责任安全、闭环评估
```

在 2025–2026 年的 GUI / Web / OS Agent 研究中，**Action-space / 动作空间定义** 已经成为核心问题之一。常见表示方式包括：

```text
Coordinate action / 坐标动作：click(x, y)、drag(x1, y1, x2, y2)、scroll(direction)
Element-tree action / 元素树动作：基于 DOM、accessibility tree 或 UI element id 选择目标
Text/tool action / 文本与工具动作：type(text)、hotkey(key)、open_app(app)、call_tool(args)
Hybrid action / 混合动作：先用视觉 grounding 找位置，再用结构化 API 或脚本执行
```

因此，评估 GUI Agent 时不能只看“答对没有”，还要看它是否能在 WebVoyager、OSWorld 等交互式 benchmark 中稳定完成可执行动作、恢复错误，并跨网页、桌面和应用工作流泛化。

</details>

<details>
<summary><strong>14.3 Upstream & Downstream / 上下游定位</strong></summary>

视觉基础模型、MLLM 与视觉智能体位于“感知结果”和“可执行任务”之间，是把图像、视频、文档和工具接口组织成任务流程的中枢层。

```text
上游输入：图像/视频/屏幕/文档、检测/分割/OCR/三维结果、文本指令、工具返回值、环境状态
本章输出：跨模态语义表征、grounding 结果、问答解释、工具调用计划、GUI/Web 操作、机器人动作草案
下游模块：开放词汇感知、自动标注、RAG、GUI / Web Agent、VLA 机器人控制、自动驾驶场景解释与决策辅助
核心边界：语言解释能力不等于空间定位、物理可执行性或闭环安全
```

判断这类论文时，要看它只是增强“看图回答”，还是已经连接到 grounding、工具调用、动作空间、环境反馈和可验证执行。

</details>

<details>
<summary><strong>14.4 Representative Works / 代表性工作速览</strong></summary>

| 年份 / Year | 方法 / Work | 位置 / Position | 为什么重要 / Why it matters |
|---:|---|---|---|
| 2021/2022 | MAE | 自监督视觉表征 | 用 masked image modeling 学习通用视觉特征 |
| 2023 | DINOv2 | 通用视觉特征 | 代表强迁移的自监督视觉基础表征 |
| 2021 | CLIP | 视觉语言对齐 | 开放词汇和语义检索基础 |
| 2023 | SAM | 可提示分割 | 将分割变成 promptable interface |
| 2023 | SAM 2 | 图像/视频统一分割 | 把可提示分割拓展到视频对象跟踪与分割 |
| 2023 | Grounding DINO | 开放文本定位 | 连接语言提示与目标检测 |
| 2023 | LLaVA | 视觉指令模型 | 代表开源看图对话模型主线 |
| 2025 | Qwen2.5-VL | 综合 MLLM / 视觉 Agent | 强调定位、文档、视频和交互能力 |
| 2025 | InternVL3 | 原生多模态预训练 | 强调多模态与语言能力共同预训练 |
| 2023–2024 | GUI grounding / GUI Agent 系列 | 屏幕智能体 | 把视觉定位与动作执行连接到软件操作 |

</details>

<details>
<summary><strong>14.5 Paper Positioning / 论文归位指引</strong></summary>

归位本章论文时，优先判断其任务输入输出、核心改动位置、目标约束和服务的下游系统。

</details>

<details>
<summary><strong>14.6 Paper Cards / 核心论文卡片</strong></summary>

> 本节集中放置本章代表论文入口。正文和代表论文表格中的方法名优先跳转到这里，外部 Paper / Code / Project 链接只在论文卡片中出现。

<a id="paper-14-mae"></a>

#### MAE

- **Title / 标题**：Masked Autoencoders Are Scalable Vision Learners
- **Year / 年份**：2021/2022
- **Core Contribution / 核心贡献**：用 masked image modeling 学习通用视觉特征。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2111.06377)
<a id="paper-14-dinov2"></a>

#### DINOv2

- **Title / 标题**：DINOv2: Learning Robust Visual Features without Supervision
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：代表强迁移的自监督视觉基础表征。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2304.07193)
<a id="paper-14-clip"></a>

#### CLIP

- **Title / 标题**：Learning Transferable Visual Models From Natural Language Supervision
- **Year / 年份**：2021
- **Core Contribution / 核心贡献**：开放词汇和语义检索基础。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2103.00020)
<a id="paper-14-sam"></a>

#### SAM

- **Title / 标题**：Segment Anything
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：将分割变成 promptable interface。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2304.02643)
<a id="paper-14-sam-2"></a>

#### SAM 2

- **Title / 标题**：SAM 2: Segment Anything in Images and Videos
- **Year / 年份**：2024
- **Core Contribution / 核心贡献**：把可提示分割拓展到视频对象跟踪与分割。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2408.00714)
<a id="paper-14-grounding-dino"></a>

#### Grounding DINO

- **Title / 标题**：Grounding DINO: Marrying DINO with Grounded Pre-Training for Open-Set Object Detection
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：连接语言提示与目标检测。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2303.05499)
<a id="paper-14-llava"></a>

#### LLaVA

- **Title / 标题**：Visual Instruction Tuning
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：代表开源看图对话模型主线。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2304.08485)
<a id="paper-14-qwen2-5-vl"></a>

#### Qwen2.5-VL

- **Title / 标题**：Qwen2.5-VL Technical Report
- **Year / 年份**：2025
- **Core Contribution / 核心贡献**：强调定位、文档、视频和交互能力。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2502.13923)
<a id="paper-14-internvl3"></a>

#### InternVL3

- **Title / 标题**：InternVL3: Exploring Advanced Training and Test-Time Recipes for Open-Source Multimodal Models
- **Year / 年份**：2025
- **Core Contribution / 核心贡献**：强调多模态与语言能力共同预训练。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2504.10479)
<a id="paper-14-gui-grounding-gui-agent-系列"></a>

#### GUI Grounding / GUI Agent 系列

- **Title / 标题**：CogAgent: A Visual Language Model for GUI Agents / WebVoyager: Building an End-to-End Web Agent with Large Multimodal Models / OSWorld: Benchmarking Multimodal Agents for Open-Ended Tasks in Real Computer Environments
- **Year / 年份**：2023–2024
- **Core Contribution / 核心贡献**：把视觉定位与动作执行连接到软件操作。
- **Links / 链接**：[CogAgent](https://arxiv.org/abs/2312.08914) / [SeeAct](https://arxiv.org/abs/2401.01614) / [WebVoyager](https://arxiv.org/abs/2401.13919) / [OSWorld](https://arxiv.org/abs/2404.07972)
</details>

## Part IV. System-level Intelligence / 系统级智能

### 15. Prediction, Planning & Dynamic World Modeling / 预测、规划与动态世界建模

<details open>
<summary><strong>15.0 Quick Overview / 一页速览</strong></summary>

```text
Prediction, Planning & Dynamic World Modeling / 预测、规划与动态世界建模

├── Prediction / 预测
│   ├── 单智能体轨迹预测
│   ├── 多智能体交互预测
│   ├── 行为意图预测
│   ├── future BEV / occupancy / video prediction
│   └── 不确定性与多模态未来
│
├── Planning / 规划
│   ├── Task Planning / 任务规划
│   ├── Behavior Planning / 行为规划
│   ├── Motion Planning / 运动规划
│   ├── Trajectory Planning / 轨迹规划
│   └── Learning-based / Diffusion-based Planning
│
├── Decision / 决策
│   ├── rule-based / FSM / behavior tree
│   ├── POMDP / game theory
│   ├── imitation learning / RL
│   └── LLM / VLM assisted decision
│
└── Dynamic World Model / 动态世界模型
    ├── 预测“世界将如何变化”
    ├── 预测“如果我这样行动，会发生什么”
    └── 为规划和控制提供可模拟的未来
```

</details>

<details>
<summary><strong>15.1 Basic Definition & Task Variants / 核心定义与任务变体</strong></summary>

#### Why Prediction and Planning Matter / 为什么预测和规划重要？

感知回答的是：

```text
现在世界是什么样？
```

预测回答的是：

```text
接下来世界可能会怎样变化？
```

规划回答的是：

```text
我应该怎么做？
```

动态世界建模回答的是：

```text
如果我采取某个动作，世界会如何响应？
```

这四个问题之间的关系非常紧密。自动驾驶里，车辆需要预测行人、车辆、红绿灯和路况变化；机器人里，机械臂需要预测物体会不会滑落、推一下会移动到哪里、开门后空间会怎样变化。

因此，预测和规划是从“看懂世界”到“改变世界”的桥梁。

</details>

<details>
<summary><strong>15.2 Method Evolution / 方法演化主线</strong></summary>

#### Trajectory Prediction / 轨迹预测

轨迹预测的发展大致可以分成：

```text
物理模型：constant velocity / constant acceleration
序列模型：RNN / LSTM / GRU
交互建模：Social LSTM / Social GAN
图结构建模：agent-agent graph / agent-map graph
Transformer：多智能体、多模态未来建模
生成式预测：CVAE / GAN / Diffusion
世界模型：预测未来 BEV、occupancy、video 或 latent state
```

新手需要抓住一个核心问题：

> 未来不是唯一答案。轨迹预测不是回归一条曲线，而是建模多种合理未来。

因此，很多论文会强调：

```text
multi-modal prediction / 多模态未来
interaction modeling / 交互建模
map-aware prediction / 地图约束
uncertainty estimation / 不确定性
closed-loop impact / 对规划的影响
```

#### Motion Planning / 运动规划

运动规划可以按方法分成几类：

```text
Graph Search / 图搜索：A*、Dijkstra、Hybrid A*
Sampling-based Planning / 采样规划：RRT、RRT*
Optimization-based Planning / 优化规划：trajectory optimization、QP、MPC
Lattice / Frenet Planning：道路结构化环境中的轨迹生成
Learning-based Planning：从数据学习规划策略
Diffusion Planning：用扩散模型生成候选轨迹或动作序列
LLM/VLM-assisted Planning：用大模型做任务分解和语义决策
```

这里要注意层级差异：

```text
Task Planning / 任务规划：先做什么，后做什么？
Behavior Planning / 行为规划：跟车、变道、让行、停车？
Motion Planning / 运动规划：具体路径和轨迹怎么走？
Control / 控制：如何让真实系统跟踪轨迹？
```

很多新手把“决策、规划、控制”混在一起，但它们关注的问题不同。

#### World Model for Planning / 面向规划的世界模型

世界模型的核心思想是：

```text
模型不仅要知道当前状态，还要能模拟未来。
```

在视觉和具身智能里，它可以表现为：

```text
future frame prediction / 未来图像预测
future video generation / 未来视频生成
future BEV prediction / 未来 BEV 预测
occupancy flow prediction / 占据流预测
latent dynamics model / 隐空间动力学模型
action-conditioned prediction / 动作条件预测
interactive world model / 交互式世界模型
```

普通预测和世界模型的区别在于：

```text
普通预测：别人接下来可能怎么动。
世界模型：如果我做 A，环境和其他智能体会如何响应。
```

这就是世界模型和规划天然相关的原因。

</details>

<details>
<summary><strong>15.3 Upstream & Downstream / 上下游定位</strong></summary>

预测、规划与动态世界建模位于感知和控制之间，是系统从“理解当前”走向“选择未来动作”的核心层。

```text
上游输入：检测/跟踪结果、地图/车道图、BEV/occupancy、历史轨迹、交通规则、目标指令
本章输出：多模态未来轨迹、风险评估、代价图、规划路径、动态世界状态或 rollout
下游模块：控制器、仿真评估、自动驾驶闭环系统、机器人导航与操作
系统价值：把感知结果转化为可执行、可评估、可约束的未来行动方案
```

</details>

<details>
<summary><strong>15.4 Representative Works / 代表性工作速览</strong></summary>

| 年份 / Year | 方法 / Work | 位置 / Position | 为什么重要 / Why it matters |
|---:|---|---|---|
| 2016 / 2018 | Social LSTM / Social GAN | 交互式轨迹预测 | 开始系统建模行人之间的社会交互 |
| 2020 | VectorNet / LaneGCN | 地图约束轨迹预测 | 用矢量地图和图结构建模 agent-map 关系 |
| 2020 | Trajectron++ | 多智能体概率预测 | 代表动态图结构和多模态未来预测路线 |
| 2020 / 2021 | TNT / DenseTNT | 目标驱动轨迹预测 | 将终点候选和轨迹生成结合 |
| 2022 | Wayformer / Motion Transformer 类方法 | Transformer 轨迹预测 | 用注意力统一建模多智能体、多模态未来 |
| 2022–2024 | Diffusion-based trajectory prediction | 生成式预测 | 用扩散模型表达多种合理未来 |
| 2019–2020 | Dreamer / MuZero | 世界模型与规划 | 强化学习中世界模型和规划结合的代表 |
| 2021–2024 | Future BEV / Occupancy prediction | 驾驶世界预测 | 将未来预测从轨迹扩展到场景级表示 |

</details>

<details>
<summary><strong>15.5 Paper Positioning / 论文归位指引</strong></summary>

```text
1. 它预测的是谁？自车、行人、车辆、机器人、物体，还是整个场景？
2. 它输出什么？轨迹、热力图、occupancy、future BEV、video、latent state？
3. 它是否考虑地图？是否考虑多智能体交互？
4. 它是 open-loop 预测，还是会影响 closed-loop planning？
5. 它是直接生成动作，还是只作为规划输入？
6. 它是否是 action-conditioned world model？
```

例子：

```text
一篇 Future Occupancy Prediction 论文
主归属：Prediction / Dynamic Scene Modeling
交叉归属：Occupancy、Autonomous Driving、World Model
下游：motion planning、risk estimation、closed-loop driving

一篇 Diffusion Planner 论文
主归属：Learning-based Motion Planning
交叉归属：Generative Model、Autonomous Driving / Robotics
核心问题：用生成模型表达多种可行轨迹
```

</details>

<details>
<summary><strong>15.6 Paper Cards / 核心论文卡片</strong></summary>

> 本节补齐第 15 章代表论文入口，修复 15.5 表格中的内部跳转失效问题。预测与规划领域的“系列工作”保留在同一张卡片中；不同独立工作不再共用泛化锚点。

<a id="paper-15-social-lstm-social-gan"></a>

#### Social LSTM / Social GAN

- **Title / 标题**：Social LSTM: Human Trajectory Prediction in Crowded Spaces / Social GAN: Socially Acceptable Trajectories with Generative Adversarial Networks
- **Year / 年份**：2016 / 2018
- **Core Contribution / 核心贡献**：Social LSTM 用邻域池化建模行人交互；Social GAN 用对抗训练生成多种社会可接受的未来轨迹。
- **Links / 链接**：[Social LSTM](https://arxiv.org/abs/1603.09461) / [Social GAN](https://arxiv.org/abs/1803.10892)
<a id="paper-15-vectornet-lanegcn"></a>

#### VectorNet / LaneGCN

- **Title / 标题**：VectorNet: Encoding HD Maps and Agent Dynamics from Vectorized Representation / Learning Lane Graph Representations for Motion Forecasting
- **Year / 年份**：2020
- **Core Contribution / 核心贡献**：VectorNet 用矢量化 polyline 编码地图和 agent 历史；LaneGCN 用车道图卷积显式建模 lane-agent 关系。
- **Links / 链接**：[VectorNet](https://arxiv.org/abs/2005.04259) / [LaneGCN](https://arxiv.org/abs/2007.13732)
<a id="paper-15-trajectron"></a>

#### Trajectron++

- **Title / 标题**：Trajectron++: Dynamically-Feasible Trajectory Forecasting With Heterogeneous Data
- **Year / 年份**：2020
- **Core Contribution / 核心贡献**：用动态图结构和 CVAE 融合 agent 交互、地图和动力学约束，生成动态可行的多模态未来轨迹。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2001.03093) / [Code](https://github.com/StanfordASL/Trajectron-plus-plus)
<a id="paper-15-tnt-densetnt"></a>

#### TNT / DenseTNT

- **Title / 标题**：TNT: Target-driven Trajectory Prediction / DenseTNT: End-to-end Trajectory Prediction from Dense Goal Sets
- **Year / 年份**：2020 / 2021
- **Core Contribution / 核心贡献**：把运动预测拆成目标点选择与轨迹生成，DenseTNT 进一步从密集目标集合端到端预测多模态轨迹。
- **Links / 链接**：[TNT](https://arxiv.org/abs/2008.08294) / [DenseTNT](https://arxiv.org/abs/2108.09640)
<a id="paper-15-wayformer-motion-transformer"></a>

#### Wayformer / Motion Transformer 类方法

- **Title / 标题**：Wayformer: Motion Forecasting via Simple & Efficient Attention Networks / Motion Transformer with Global Intention Localization and Local Movement Refinement
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：用注意力统一编码道路图、历史轨迹和多 agent 交互；Motion Transformer 进一步以意图定位和局部轨迹细化建模多模态未来。
- **Links / 链接**：[Wayformer](https://arxiv.org/abs/2207.05844) / [Motion Transformer](https://arxiv.org/abs/2209.13508)
<a id="paper-15-diffusion-based-trajectory-prediction"></a>

#### Diffusion-based Trajectory Prediction

- **Title / 标题**：Diffusion-based Trajectory Prediction and Planning Methods
- **Year / 年份**：2022–2024
- **Core Contribution / 核心贡献**：用扩散过程建模多模态轨迹或动作序列，适合生成多种可行未来，并可与代价函数、约束或规划目标结合。
- **Links / 链接**：[MID](https://arxiv.org/abs/2209.02450) / [Diffuser](https://arxiv.org/abs/2205.09991)
<a id="paper-15-dreamer-muzero"></a>

#### Dreamer / MuZero

- **Title / 标题**：Dream to Control: Learning Behaviors by Latent Imagination / Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model
- **Year / 年份**：2019–2020
- **Core Contribution / 核心贡献**：Dreamer 在潜变量中想象 rollout 学控制策略；MuZero 学隐式动力学、价值和策略，并通过搜索完成规划。
- **Links / 链接**：[Dreamer](https://arxiv.org/abs/1912.01603) / [MuZero](https://arxiv.org/abs/1911.08265)
<a id="paper-15-future-bev-occupancy-prediction"></a>

#### Future BEV / Occupancy Prediction

- **Title / 标题**：Future BEV / Occupancy Prediction for Dynamic World Modeling in Autonomous Driving
- **Year / 年份**：2021–2024
- **Core Contribution / 核心贡献**：把 BEV 从当前帧感知扩展为未来时空预测，用于建模动态占据、运动场和面向规划的世界状态。
- **Links / 链接**：[FIERY](https://arxiv.org/abs/2104.10490) / [StretchBEV](https://arxiv.org/abs/2203.13641) / [OccWorld](https://arxiv.org/abs/2311.16038)
</details>

### 16. Autonomous Driving Research Map / 自动驾驶研究地图

<details open>
<summary><strong>16.0 Quick Overview / 一页速览</strong></summary>

```text
Autonomous Driving / 自动驾驶

├── 系统链条
│   Sensors → Calibration → Perception → Tracking → Prediction → Planning → Control → Evaluation
│
├── 感知与表征
│   ├── 2D perception：检测、分割、车道线、交通灯、可行驶区域
│   ├── 3D perception：3D detection、point cloud segmentation、depth、scene flow
│   ├── BEV：把多相机、多模态信息统一到鸟瞰图
│   ├── Occupancy：从检测框走向空间占据表示
│   └── HD Map / Online Mapping / Vectorized Map
│
├── 预测与规划
│   ├── 轨迹预测
│   ├── 行为决策
│   ├── 运动规划
│   ├── 规划导向感知
│   └── closed-loop evaluation
│
├── 端到端自动驾驶
│   ├── Sensor-to-control
│   ├── Sensor-to-trajectory
│   ├── Perception-to-planning
│   ├── Planning-oriented unified model
│   └── VLM / World Model enhanced driving
│
└── 新主线
    ├── Foundation Model for Driving
    ├── VLM-assisted Driving
    ├── World Model for Driving
    ├── Scenario Generation
    └── Safety / Verification / Data Engine
```

</details>

<details>
<summary><strong>16.1 Basic Definition & Task Variants / 核心定义与任务变体</strong></summary>

本章主要围绕该领域的核心任务定义、常见输入输出形式和任务变体展开。

</details>

<details>
<summary><strong>16.2 Method Evolution / 方法演化主线</strong></summary>

#### Modular Pipeline / 模块化自动驾驶

经典自动驾驶系统通常是模块化 pipeline：

```text
传感器输入
→ 感知：检测车辆、行人、车道线、交通灯
→ 跟踪：维护目标 ID 和状态
→ 预测：预测其他交通参与者未来轨迹
→ 决策：跟车、让行、变道、超车、停车
→ 规划：生成自车未来轨迹
→ 控制：方向盘、油门、刹车跟踪轨迹
```

模块化系统的优点是：

```text
可解释、可调试、便于工程安全验证。
```

缺点是：

```text
误差逐级传递；
每个模块的指标不一定服务最终驾驶质量；
模块之间接口复杂，系统优化困难。
```

#### Representation Evolution / 表征演化主线

自动驾驶感知最关键的变化之一，是表征从“图像和检测框”走向“规划友好的空间表示”。

```text
Image Space / 图像空间
→ 2D detection、lane detection、semantic segmentation

Point Cloud Space / 点云空间
→ LiDAR 3D detection、point cloud segmentation

BEV / 鸟瞰图
→ 多相机、多模态统一空间，适合地图、轨迹、规划

Vectorized Map / 矢量地图
→ 车道线、道路边界、拓扑结构、交通规则

Occupancy / 占据表示
→ 不再只描述已知物体，而是描述空间是否被占据、是否可通行

Latent World State / 隐空间世界状态
→ 面向端到端规划或世界模型的压缩状态表示
```

新手要理解：

> 自动驾驶感知的终点不是“mAP 更高”，而是“这个表征是否更适合预测、规划和安全驾驶”。

#### End-to-End Driving / 端到端自动驾驶

端到端自动驾驶不是一个单一方法，而是一组范式：

```text
Sensor-to-control：从图像直接输出方向盘、油门、刹车。
Sensor-to-trajectory：从传感器直接输出未来轨迹。
Perception-to-planning：用 BEV、occupancy、map 等中间表示输出规划。
Unified model：感知、预测、规划在同一模型内协同优化。
VLM-assisted driving：用视觉语言模型辅助场景理解和高层决策。
World-model-based driving：学习未来场景，用模拟未来辅助规划。
```

端到端的核心动机是：

```text
不再只优化单模块指标，而是让系统最终服务驾驶规划。
```

但它的问题也很明显：

```text
可解释性弱；
安全验证难；
长尾场景风险高；
闭环评估成本高；
大模型实时部署困难。
```

#### VLM and Foundation Models for Driving / 驾驶中的 VLM 与基础模型

驾驶场景天然包含视觉、语言、规则、地图和行动，因此非常适合引入基础模型。但必须谨慎理解：

```text
VLM 可以帮助解释复杂场景、理解交通语义、处理长尾案例；
但 VLM 并不天然擅长精确几何、实时控制和安全验证。
```

例如 DriveVLM 这类方法尝试把视觉语言模型用于驾驶场景描述、场景分析和层级规划。它的意义不是“用大模型直接开车”，而是展示了 VLM 可以作为语义理解和推理模块补充传统驾驶 pipeline。

自动驾驶基础模型相关方向可以分为：

```text
Perception Foundation Model / 感知基础模型
Scenario Generation / 场景生成
Scenario Understanding / 场景分析
VLM-assisted Decision / VLM 辅助决策
World Model for Driving / 驾驶世界模型
Data Engine / 数据闭环与长尾挖掘
```

</details>

<details>
<summary><strong>16.3 Upstream & Downstream / 上下游定位</strong></summary>

自动驾驶系统级地图把前面章节的模块串成闭环工程链条。

```text
上游输入：传感器、标定、地图、感知/跟踪/预测模块、仿真与路测数据
本章输出：完整驾驶任务链路、模块接口、系统评估维度、数据闭环问题清单
下游模块：规划控制、仿真回放、安全验证、车端部署、数据挖掘与模型迭代
系统价值：把单点算法放回车辆系统，评估它是否真的改善闭环驾驶能力
```

</details>

<details>
<summary><strong>16.4 Representative Works / 代表性工作速览</strong></summary>

| 年份 / Year | 方法 / Work | 位置 / Position | 为什么重要 / Why it matters |
|---:|---|---|---|
| 1989 / 2016 | ALVINN / DAVE-2 | 早期端到端驾驶 | 证明从视觉到控制的端到端想法可行，但安全与泛化不足 |
| 2020 | Lift-Splat-Shoot | Camera BEV | 多相机图像到 BEV 表征的重要节点 |
| 2022 | BEVFormer | BEV Transformer | 用时空注意力建模多相机 BEV 感知 |
| 2022 | BEVFusion / TransFusion | 多模态 3D 感知 | LiDAR-camera 融合和 BEV 融合代表 |
| 2021–2022 | HDMapNet / VectorMapNet | 在线地图构建 | 从感知生成矢量化道路结构 |
| 2023 | UniAD | planning-oriented unified driving | 将感知、预测、规划任务按规划目标统一组织 |
| 2023 | VAD | vectorized end-to-end driving | 用矢量化 agent 和地图元素作为规划约束 |
| 2024 | DriveVLM | VLM-assisted driving | 用 VLM 辅助场景理解与层级规划 |
| 2025 | BridgeAD | 端到端驾驶历史-未来桥接 | 用历史预测和规划增强端到端驾驶 |
| 2025 | World Models for Autonomous Driving Survey | 驾驶世界模型综述 | 系统梳理驾驶场景生成、预测和规划交互 |

</details>

<details>
<summary><strong>16.5 Paper Positioning / 论文归位指引</strong></summary>

读自动驾驶论文时，不要先问“它是不是端到端”。先问：

```text
1. 它研究系统哪一层？感知、地图、预测、规划、控制、评估，还是数据闭环？
2. 它的输入是什么？camera、LiDAR、radar、map、language、multi-modal？
3. 它的输出是什么？bbox、BEV、occupancy、map、trajectory、control、risk？
4. 它的表征是什么？image、point cloud、BEV、occupancy、vector map、latent state？
5. 它是否服务 planning？是否有 closed-loop evaluation？
6. 它是模块化、多任务统一、端到端、VLM-assisted，还是 world-model-based？
```

例子：

```text
UniAD
主归属：End-to-End Autonomous Driving / Planning-oriented Unified Model
交叉归属：Tracking、Prediction、Occupancy、Planning
核心贡献：以最终规划为导向组织多个驾驶任务

VAD
主归属：Vectorized End-to-End Driving
交叉归属：Vector Map、Trajectory Planning、Efficient Planning
核心贡献：用矢量化场景表示提高规划效率和安全性

DriveVLM
主归属：VLM-assisted Driving
交叉归属：Scene Understanding、Decision Reasoning、Autonomous Driving Agent
核心贡献：用视觉语言模型增强长尾场景理解和层级规划
```

</details>

<details>
<summary><strong>16.6 Paper Cards / 核心论文卡片</strong></summary>

> 本节集中放置本章代表论文入口。正文和代表论文表格中的方法名优先跳转到这里，外部 Paper / Code / Project 链接只在论文卡片中出现。

<a id="paper-16-alvinn-dave-2"></a>

#### ALVINN / DAVE-2

- **Title / 标题**：ALVINN: An Autonomous Land Vehicle in a Neural Network / End to End Learning for Self-Driving Cars
- **Year / 年份**：1989 / 2016
- **Core Contribution / 核心贡献**：证明从视觉到控制的端到端想法可行，但安全与泛化不足。
- **Links / 链接**：[ALVINN](https://isl.ecst.csuchico.edu/DOCS/pub/ai/papers/89ALVINN.pdf) / [DAVE-2](https://arxiv.org/abs/1604.07316)
<a id="paper-16-lift-splat-shoot"></a>

#### Lift-Splat-Shoot

- **Title / 标题**：Lift, Splat, Shoot: Encoding Images from Arbitrary Camera Rigs by Implicitly Unprojecting to 3D
- **Year / 年份**：2020
- **Core Contribution / 核心贡献**：多相机图像到 BEV 表征的重要节点。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2008.05711)
<a id="paper-16-bevformer"></a>

#### BEVFormer

- **Title / 标题**：BEVFormer: Learning Bird's-Eye-View Representation from Multi-Camera Images via Spatiotemporal Transformers
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：用时空注意力建模多相机 BEV 感知。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2203.17270) / [Code](https://github.com/fundamentalvision/BEVFormer)
<a id="paper-16-bevfusion-transfusion"></a>

#### BEVFusion / TransFusion

- **Title / 标题**：BEVFusion: Multi-Task Multi-Sensor Fusion with Unified Bird's-Eye View Representation / TransFusion: Robust LiDAR-Camera Fusion for 3D Object Detection with Transformers
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：LiDAR-camera 融合和 BEV 融合代表。
- **Links / 链接**：[BEVFusion](https://arxiv.org/abs/2205.13542) / [TransFusion](https://arxiv.org/abs/2203.11496)
<a id="paper-16-hdmapnet-vectormapnet"></a>

#### HDMapNet / VectorMapNet

- **Title / 标题**：HDMapNet: An Online HD Map Construction and Evaluation Framework / VectorMapNet: End-to-end Vectorized HD Map Learning
- **Year / 年份**：2021–2022
- **Core Contribution / 核心贡献**：从感知生成矢量化道路结构。
- **Links / 链接**：[HDMapNet](https://arxiv.org/abs/2107.06307) / [VectorMapNet](https://arxiv.org/abs/2206.08920)
<a id="paper-16-uniad"></a>

#### UniAD

- **Title / 标题**：Planning-oriented Autonomous Driving
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：将感知、预测、规划任务按规划目标统一组织。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2212.10156)
<a id="paper-16-vad"></a>

#### VAD

- **Title / 标题**：VAD: Vectorized Scene Representation for Efficient Autonomous Driving
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：用矢量化 agent 和地图元素作为规划约束。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2303.12077)
<a id="paper-16-drivevlm"></a>

#### DriveVLM

- **Title / 标题**：DriveVLM: The Convergence of Autonomous Driving and Large Vision-Language Models
- **Year / 年份**：2024
- **Core Contribution / 核心贡献**：用 VLM 辅助场景理解与层级规划。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2402.12289)
<a id="paper-16-bridgead"></a>

#### BridgeAD

- **Title / 标题**：BridgeAD: Bridging Past and Future for End-to-End Autonomous Driving with Historical Prediction and Planning
- **Year / 年份**：2025
- **Core Contribution / 核心贡献**：用历史预测和规划增强端到端驾驶。
- **Links / 链接**：[Paper](https://openaccess.thecvf.com/content/CVPR2025/papers/Zhang_Bridging_Past_and_Future_End-to-End_Autonomous_Driving_with_Historical_Prediction_CVPR_2025_paper.pdf)
<a id="paper-16-world-models-for-autonomous-driving-survey"></a>

#### World Models for Autonomous Driving Survey

- **Title / 标题**：World Models for Autonomous Driving: An Initial Survey
- **Year / 年份**：2025
- **Core Contribution / 核心贡献**：系统梳理驾驶场景生成、预测和规划交互。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2501.11260)
</details>

### 17. Embodied AI Research Map / 具身智能研究地图

<details open>
<summary><strong>17.0 Quick Overview / 一页速览</strong></summary>

```text
Embodied AI / 具身智能

├── 核心问题
│   ├── 智能体不仅要看懂世界，还要在物理世界中行动
│   ├── 需要处理感知、语言、空间、记忆、规划、控制、接触物理
│   └── 最终目标是完成长程、开放、可泛化的真实任务
│
├── 任务主线
│   ├── Navigation / 导航：PointNav、ObjectNav、VLN、EQA
│   ├── Manipulation / 操作：抓取、放置、推、拉、插入、折叠、倒水、工具使用
│   ├── Task and Motion Planning / 任务与运动规划
│   ├── Human-Robot Interaction / 人机交互
│   ├── Skill Learning / 技能学习
│   └── Generalist Robot Policy / 通用机器人策略
│
├── 学习范式
│   ├── imitation learning / 模仿学习
│   ├── behavior cloning / 行为克隆
│   ├── reinforcement learning / 强化学习
│   ├── offline RL / 离线强化学习
│   ├── diffusion policy / 扩散策略
│   ├── VLA / 视觉-语言-动作模型
│   └── world-model-based policy / 基于世界模型的策略
│
└── 新主线
    ├── Internet-scale vision-language pretraining
    ├── robot demonstration data
    ├── cross-embodiment transfer
    ├── generalist policy
    ├── humanoid foundation model
    └── safety and deployment
```

</details>

<details>
<summary><strong>17.1 Basic Definition & Task Variants / 核心定义与任务变体</strong></summary>

#### Embodiment First / 先理解“本体”

具身智能和普通视觉最大的区别是：

```text
视觉模型只需要输出答案；
具身智能体必须在物理世界中执行动作，并承担动作后果。
```

不同机器人本体会改变任务难度：

```text
机械臂：抓取、放置、插入、装配、工具使用。
移动机器人：导航、避障、探索、巡检。
移动机械臂：导航 + 操作，难度显著增加。
四足机器人：复杂地形移动、身体稳定。
人形机器人：全身控制、双手操作、人与环境兼容。
无人机：空中导航、视角变化、动力学约束。
灵巧手：精细接触、柔顺控制、高维动作空间。
```

所以同一篇“机器人学习”论文，必须看清它在哪种本体上验证。机械臂 tabletop manipulation 的成功，不能直接等同于人形机器人家庭服务任务成功。

</details>

<details>
<summary><strong>17.2 Method Evolution / 方法演化主线</strong></summary>

#### Navigation / 导航主线

具身导航从简单到复杂可以分成：

```text
PointNav / 点目标导航：走到指定坐标。
ObjectNav / 目标物导航：找到某类物体，比如 chair。
ImageNav / 图像目标导航：走到和目标图像相似的位置。
VLN / 视觉语言导航：根据自然语言路线指令导航。
EQA / 具身问答：为了回答问题主动探索环境。
Social Navigation / 社会导航：在人群中礼貌、安全地移动。
```

这条线的技术演化是：

```text
几何地图与 SLAM
→ 语义地图
→ 拓扑地图
→ 记忆增强策略
→ 语言条件导航
→ LLM/VLM-assisted planning
→ 长程具身智能体
```

VLN 尤其重要，因为它把视觉、语言、空间记忆和动作决策连在一起，是 VLA 和具身 Agent 的前身之一。

#### Manipulation / 操作主线

机器人操作比导航更难，因为它涉及接触、力、摩擦、形变、遮挡和动作精度。

操作任务可以从简单到复杂分成：

```text
grasping / 抓取
placing / 放置
pushing / 推
pulling / 拉
insertion / 插入
pouring / 倒水
folding / 折叠
cutting / 切割
tool use / 工具使用
bimanual manipulation / 双臂操作
dexterous manipulation / 灵巧手操作
whole-body manipulation / 全身操作
```

方法演化可以这样理解：

```text
解析几何抓取
→ 深度学习抓取检测
→ 模仿学习和行为克隆
→ 强化学习与仿真训练
→ offline RL 与大规模示范数据
→ diffusion policy
→ VLA / robot foundation model
```

在现代机器人学习里，扩散策略很重要，因为它擅长建模连续动作序列的多模态分布；VLA 进一步把视觉、语言和动作放到统一模型里。

#### Vision-Language-Action Models / 视觉-语言-动作模型

VLA 的核心是：

```text
输入：视觉观测 + 语言指令 + 机器人状态
输出：机器人动作
```

它和普通 VLM 的区别是：

```text
VLM 输出文本；
VLA 输出可执行动作。
```

它和传统机器人策略的区别是：

```text
传统策略往往针对单任务、单机器人、单环境训练；
VLA 希望利用互联网视觉语言知识和机器人示范数据，获得更强泛化能力。
```

这条主线可以这样看：

```text
RT-1：大规模机器人 Transformer 策略
RT-2：把网络视觉语言知识迁移到机器人动作
Open X-Embodiment / RT-X：跨机器人数据和策略
Octo：开源通用机器人策略
OpenVLA：开源 7B VLA，基于大规模真实机器人示范
π0：基于 VLM 与 flow matching 的通用机器人策略
Gemini Robotics：面向机器人控制和具身推理的 VLA 系列
GR00T：面向人形机器人的通用基础模型
```

VLA 不是“终点”，而是一个过渡范式：它把语言、视觉、动作统一起来，但仍然面临长程任务、精细接触、安全验证、跨本体泛化等挑战。

</details>

<details>
<summary><strong>17.3 Upstream & Downstream / 上下游定位</strong></summary>

具身智能把视觉和语言接到物理世界中的动作执行。

```text
上游输入：机器人相机、深度/触觉/本体状态、语言指令、环境地图、示教数据或仿真数据
本章输出：导航策略、抓取/操作动作、VLA action token、任务计划、失败恢复策略
下游模块：移动机器人、机械臂、家务/仓储/工业操作、仿真到真实迁移、安全执行
系统价值：检验视觉理解是否能变成物理世界中可执行、可恢复、可泛化的行为
```

</details>

<details>
<summary><strong>17.4 Representative Works / 代表性工作速览</strong></summary>

| 年份 / Year | 方法 / Work | 位置 / Position | 为什么重要 / Why it matters |
|---:|---|---|---|
| 2017–2019 | Habitat / AI2-THOR / Gibson / Matterport3D | 具身仿真环境 | 为导航、EQA、交互任务提供模拟平台 |
| 2018 | Room-to-Room / VLN | 视觉语言导航 | 连接自然语言指令、视觉观察和动作路径 |
| 2021/2022 | CLIPort | language-conditioned manipulation | 用 CLIP 语义引导操作策略 |
| 2022 | SayCan | LLM + affordance | 用语言模型分解任务，用可供性判断可执行动作 |
| 2023 | PaLM-E | embodied multimodal model | 把视觉、语言、机器人状态输入大模型 |
| 2023 | Diffusion Policy | 机器人动作生成 | 用扩散模型生成连续动作序列 |
| 2023 | RT-2 | VLA | 将网络视觉语言知识迁移到机器人控制 |
| 2023 | Open X-Embodiment / RT-X | 跨机器人数据与策略 | 构建大规模跨本体机器人学习数据 |
| 2024 | Octo | 开源通用机器人策略 | 基于 Open X-Embodiment 训练，可适配不同机器人 |
| 2024 | OpenVLA | 开源 VLA | 7B VLA，训练于大规模真实机器人示范 |
| 2024 | π0 | VLA flow model | 用 VLM 预训练和 flow matching 生成高频连续动作 |
| 2025 | Gemini Robotics | VLA + embodied reasoning | 把 Gemini 系列能力扩展到机器人控制和具身推理 |
| 2025 | GR00T N1 | 人形机器人基础模型 | 面向通用人形机器人，结合视觉语言与动作生成 |

</details>

<details>
<summary><strong>17.5 Paper Positioning / 论文归位指引</strong></summary>

读具身智能论文时，先问：

```text
1. 它的本体是什么？机械臂、移动机器人、人形、四足、无人机，还是仿真 agent？
2. 它解决什么任务？导航、抓取、操作、长程任务、工具使用、交互？
3. 它输入什么？RGB、RGB-D、点云、语言、触觉、机器人状态、历史记忆？
4. 它输出什么？离散动作、连续控制、轨迹、技能序列、语言计划？
5. 它使用什么学习范式？BC、IL、RL、offline RL、diffusion policy、VLA、world model？
6. 它是否真实机器人验证？是否跨本体、跨任务、跨环境泛化？
```

例子：

```text
OpenVLA
主归属：Vision-Language-Action Model / 机器人通用策略
交叉归属：多模态理解、机器人操作、开放词汇指令执行
核心贡献：开源大规模 VLA，支持新任务微调

π0
主归属：Generalist Robot Policy / VLA Flow Model
交叉归属：Diffusion/Flow Policy、VLM、Robot Foundation Model
核心贡献：用 flow matching 建模高频连续动作，面向复杂灵巧任务

GR00T N1
主归属：Humanoid Robot Foundation Model
交叉归属：VLA、双系统架构、人形机器人控制
核心贡献：面向通用人形机器人，把视觉语言理解与动作生成结合
```

</details>

<details>
<summary><strong>17.6 Paper Cards / 核心论文卡片</strong></summary>

> 本节集中放置本章代表论文入口。正文和代表论文表格中的方法名优先跳转到这里，外部 Paper / Code / Project 链接只在论文卡片中出现。

<a id="paper-17-habitat-ai2-thor-gibson-matterport3d"></a>

#### Habitat / AI2-THOR / Gibson / Matterport3D

- **Title / 标题**：Habitat / AI2-THOR / Gibson Environment / Matterport3D
- **Year / 年份**：2017–2019
- **Core Contribution / 核心贡献**：为导航、EQA、交互任务提供模拟平台。
- **Links / 链接**：[Habitat](https://arxiv.org/abs/1904.01201) / [AI2-THOR](https://arxiv.org/abs/1712.05474) / [Gibson](https://arxiv.org/abs/1808.10654) / [Matterport3D](https://arxiv.org/abs/1709.06158)
<a id="paper-17-room-to-room-vln"></a>

#### Room-to-Room / VLN

- **Title / 标题**：Vision-and-Language Navigation: Interpreting Visually-Grounded Navigation Instructions in Real Environments
- **Year / 年份**：2018
- **Core Contribution / 核心贡献**：连接自然语言指令、视觉观察和动作路径。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1711.07280)
<a id="paper-17-cliport"></a>

#### CLIPort

- **Title / 标题**：CLIPort: What and Where Pathways for Robotic Manipulation
- **Year / 年份**：2021/2022
- **Core Contribution / 核心贡献**：用 CLIP 语义引导操作策略。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2109.12098)
<a id="paper-17-saycan"></a>

#### SayCan

- **Title / 标题**：Do As I Can, Not As I Say: Grounding Language in Robotic Affordances
- **Year / 年份**：2022
- **Core Contribution / 核心贡献**：用语言模型分解任务，用可供性判断可执行动作。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2204.01691) / [Project](https://say-can.github.io/)
<a id="paper-17-palm-e"></a>

#### PaLM-E

- **Title / 标题**：PaLM-E: An Embodied Multimodal Language Model
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：把视觉、语言、机器人状态输入大模型。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2303.03378)
<a id="paper-17-diffusion-policy"></a>

#### Diffusion Policy

- **Title / 标题**：Diffusion Policy: Visuomotor Policy Learning via Action Diffusion
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：用扩散模型生成连续动作序列。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2303.04137) / [Project](https://diffusion-policy.cs.columbia.edu/)
<a id="paper-17-rt-2"></a>

#### RT-2

- **Title / 标题**：RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：将网络视觉语言知识迁移到机器人控制。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2307.15818)
<a id="paper-17-open-x-embodiment-rt-x"></a>

#### Open X-Embodiment / RT-X

- **Title / 标题**：Open X-Embodiment: Robotic Learning Datasets and RT-X Models
- **Year / 年份**：2023
- **Core Contribution / 核心贡献**：构建大规模跨本体机器人学习数据。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2310.08864)
<a id="paper-17-octo"></a>

#### Octo

- **Title / 标题**：Octo: An Open-Source Generalist Robot Policy
- **Year / 年份**：2024
- **Core Contribution / 核心贡献**：基于 Open X-Embodiment 训练，可适配不同机器人。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2405.12213)
<a id="paper-17-openvla"></a>

#### OpenVLA

- **Title / 标题**：OpenVLA: An Open-Source Vision-Language-Action Model
- **Year / 年份**：2024
- **Core Contribution / 核心贡献**：7B VLA，训练于大规模真实机器人示范。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2406.09246)
<a id="paper-17-pi0"></a>

#### π0

- **Title / 标题**：π0: A Vision-Language-Action Flow Model for General Robot Control
- **Year / 年份**：2024
- **Core Contribution / 核心贡献**：用 VLM 预训练和 flow matching 生成高频连续动作。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2410.24164)
<a id="paper-17-gemini-robotics"></a>

#### Gemini Robotics

- **Title / 标题**：Gemini Robotics: Bringing AI into the Physical World
- **Year / 年份**：2025
- **Core Contribution / 核心贡献**：把 Gemini 系列能力扩展到机器人控制和具身推理。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2503.20020)
<a id="paper-17-gr00t-n1"></a>

#### GR00T N1

- **Title / 标题**：GR00T N1: An Open Foundation Model for Generalist Humanoid Robots
- **Year / 年份**：2025
- **Core Contribution / 核心贡献**：面向通用人形机器人，结合视觉语言与动作生成。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2503.14734)
</details>

### 18. World Models & Simulation / 世界模型与仿真

<details open>
<summary><strong>18.0 Quick Overview / 一页速览</strong></summary>

```text
World Models & Simulation / 世界模型与仿真

├── 核心问题
│   ├── 模型能不能学习世界如何演化？
│   ├── 模型能不能预测动作后果？
│   ├── 模型能不能用于规划、训练、评估和数据生成？
│
├── 世界模型类型
│   ├── latent dynamics model / 隐空间动力学
│   ├── video prediction model / 视频预测
│   ├── action-conditioned video model / 动作条件视频模型
│   ├── BEV / occupancy world model / 驾驶空间世界模型
│   ├── physics-aware world model / 物理感知世界模型
│   ├── generative simulator / 生成式仿真器
│   └── interactive world model / 可交互世界模型
│
├── 应用场景
│   ├── reinforcement learning / 强化学习
│   ├── autonomous driving / 自动驾驶
│   ├── robotics / 机器人
│   ├── game AI / 游戏智能体
│   ├── digital twin / 数字孪生
│   └── safety testing / 安全测试
│
└── 与其他模块关系
    ├── 图像生成：生成可能画面
    ├── 视频生成：生成未来时序
    ├── NeRF / 3DGS：提供可渲染三维场景
    ├── 预测：建模未来状态
    ├── 规划：比较不同动作后果
    └── 仿真：构造训练与评估环境
```

</details>

<details>
<summary><strong>18.1 Basic Definition & Task Variants / 核心定义与任务变体</strong></summary>

#### What Is a World Model? / 什么是世界模型？

世界模型可以用一句话理解：

> 它是智能体内部的“可模拟世界”。

更具体地说，它要学习：

```text
state_t + action_t → state_{t+1}
```

或者在视觉系统中：

```text
当前图像 / 视频 / BEV / occupancy + 动作
→ 未来图像 / 未来 BEV / 未来 occupancy / 未来 latent state
```

普通生成模型和世界模型的区别在于：

```text
普通生成模型：生成看起来合理的内容。
世界模型：生成与当前状态、动作和物理规律一致的未来。
```

</details>

<details>
<summary><strong>18.2 Method Evolution / 方法演化主线</strong></summary>

#### World Model for Autonomous Driving / 自动驾驶世界模型

自动驾驶世界模型主要有三类用途：

```text
1. Scenario Generation / 场景生成
生成多样化、长尾、危险但可控的驾驶场景，用于训练和测试。

2. Future Prediction / 未来预测
预测未来视频、BEV、occupancy、交通参与者行为和场景演化。

3. Planning Interaction / 规划交互
模拟“如果自车这样走，其他车辆和环境会如何变化”，辅助决策与规划。
```

这和普通轨迹预测的区别是：

```text
轨迹预测通常关注其他 agent 的未来；
驾驶世界模型关注整个驾驶场景的未来，并可能条件化于自车动作。
```

#### World Model for Robotics / 机器人世界模型

机器人世界模型要解决的问题更复杂，因为机器人会直接改变物体状态：

```text
推一下物体会移动到哪里？
抓取是否会成功？
杯子会不会倒？
布料折叠后形状如何变化？
抽屉拉开后内部空间是什么？
```

机器人世界模型通常需要结合：

```text
视觉预测
物理常识
接触动力学
物体状态变化
动作条件生成
任务记忆
```

它的理想用途是：

```text
先在内部模拟多个动作后果，再选择最安全、最可能成功的动作。
```

但真实物理世界中的接触、摩擦、柔性物体、遮挡和长程误差累积，使机器人世界模型仍然非常困难。

#### Simulation, Digital Twin & Generative Data / 仿真、数字孪生与生成数据

仿真不只是“做一个游戏环境”。在自动驾驶和机器人中，仿真承担三种角色：

```text
Training / 训练：在模拟环境中收集大量交互数据。
Testing / 测试：构造危险、稀有、边界场景。
Debugging / 调试：复现失败案例，分析系统行为。
```

传统仿真依赖人工建模、规则和物理引擎；生成式仿真希望用数据驱动方式生成更真实、更丰富、更长尾的场景。

NeRF 和 3DGS 也与仿真有关：

```text
NeRF / 3DGS 提供可渲染三维场景；
世界模型提供随时间和动作变化的动态规律；
生成式模型提供新场景、新天气、新交通参与者、新物体外观。
```

三者结合，可能形成未来自动驾驶和具身智能的重要数据引擎。

</details>

<details>
<summary><strong>18.3 Upstream & Downstream / 上下游定位</strong></summary>

世界模型与仿真是连接数据、学习和闭环评估的环境层。

```text
上游输入：真实日志、传感器序列、地图、3D/4D 场景表示、动作和奖励/代价信号
本章输出：可预测未来状态、可交互仿真环境、合成数据、评测场景和反事实 rollout
下游模块：自动驾驶闭环评估、机器人策略学习、数据增强、安全测试、规划验证
系统价值：用可控环境和可预测动态降低真实世界试错成本
```

</details>

<details>
<summary><strong>18.4 Representative Works / 代表性工作速览</strong></summary>

| 年份 / Year | 方法 / Work | 位置 / Position | 为什么重要 / Why it matters |
|---:|---|---|---|
| 2018 | World Models | 强化学习世界模型 | 早期提出在隐空间中学习环境动力学并用于控制 |
| 2019–2023 | Dreamer 系列 | latent dynamics + RL | 代表基于隐空间世界模型的强化学习路线 |
| 2019/2020 | MuZero | model-based planning | 不显式建模真实状态，而学习对规划有用的动态模型 |
| 2016–2024 | Video prediction / diffusion video models | 视觉未来生成 | 为动作条件预测和生成式仿真提供基础 |
| 2023–2024 | GAIA-1 / driving generative world models | 驾驶视频世界模型 | 代表把视频生成用于驾驶场景建模的方向 |
| 2024 | DriveGenVLM | 驾驶视频生成 + VLM | 用生成驾驶视频辅助视觉语言理解 |
| 2018 | World Models for Autonomous Driving Survey | 自动驾驶世界模型综述 | 将驾驶世界模型分为场景生成、预测、规划交互等方向 |
| 2020 / 2023 | NeRF / 3DGS | 可渲染场景表示 | 为数字孪生和闭环仿真提供三维视觉基础 |
| 2017–2022 | Habitat / Isaac Sim / CARLA / nuPlan | 仿真与评估平台 | 具身、驾驶、机器人系统评估的重要基础设施 |

</details>

<details>
<summary><strong>18.5 Paper Positioning / 论文归位指引</strong></summary>

```text
1. 它建模的是图像、视频、BEV、occupancy、latent state，还是物理状态？
2. 它是否 action-conditioned？是否能回答“如果我这样做会怎样”？
3. 它服务训练、预测、规划、仿真，还是安全测试？
4. 它是用于自动驾驶、机器人、游戏，还是通用视频生成？
5. 它是否闭环？能否让智能体在模型内部 rollout 并选择动作？
6. 它如何评估？图像质量、预测准确率、规划收益、闭环安全，还是 sim-to-real？
```

例子：

```text
一篇 Future BEV World Model 论文
主归属：Autonomous Driving World Model
交叉归属：Prediction、BEV、Planning
核心问题：用未来 BEV 或 occupancy 支持驾驶规划

一篇 Robot Action-conditioned Video Prediction 论文
主归属：Robotics World Model
交叉归属：Video Generation、Planning、Manipulation
核心问题：根据机器人动作预测物体状态变化
```

</details>

<details>
<summary><strong>18.6 Paper Cards / 核心论文卡片</strong></summary>

> 本节集中放置本章代表论文入口。正文和代表论文表格中的方法名优先跳转到这里，外部 Paper / Code / Project 链接只在论文卡片中出现。

<a id="paper-18-world-models"></a>

#### World Models

- **Title / 标题**：World Models
- **Year / 年份**：2018
- **Core Contribution / 核心贡献**：早期提出在隐空间中学习环境动力学并用于控制。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1803.10122) / [Project](https://worldmodels.github.io/)
<a id="paper-18-dreamer-系列"></a>

#### Dreamer 系列

- **Title / 标题**：Dream to Control: Learning Behaviors by Latent Imagination / Mastering Atari with Discrete World Models / Mastering Diverse Domains through World Models
- **Year / 年份**：2019–2023
- **Core Contribution / 核心贡献**：代表基于隐空间世界模型的强化学习路线。
- **Links / 链接**：[Dreamer](https://arxiv.org/abs/1912.01603) / [DreamerV2](https://arxiv.org/abs/2010.02193) / [DreamerV3](https://arxiv.org/abs/2301.04104)
<a id="paper-18-muzero"></a>

#### MuZero

- **Title / 标题**：Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model
- **Year / 年份**：2019/2020
- **Core Contribution / 核心贡献**：不显式建模真实状态，而学习对规划有用的动态模型。
- **Links / 链接**：[Paper](https://arxiv.org/abs/1911.08265)
<a id="paper-18-video-prediction-diffusion-video-models"></a>

#### Video prediction / diffusion video models

- **Title / 标题**：Video Prediction / Video Diffusion Models
- **Year / 年份**：2016–2024
- **Core Contribution / 核心贡献**：为动作条件预测和生成式仿真提供基础。
- **Links / 链接**：[Video Diffusion Models](https://arxiv.org/abs/2204.03458) / [VideoPoet](https://arxiv.org/abs/2312.14125)
<a id="paper-18-gaia-1-driving-generative-world-models"></a>

#### GAIA-1 / driving generative world models

- **Title / 标题**：GAIA-1: A Generative World Model for Autonomous Driving / Driving Generative World Models
- **Year / 年份**：2023–2024
- **Core Contribution / 核心贡献**：代表把视频生成用于驾驶场景建模的方向。
- **Links / 链接**：[GAIA-1](https://arxiv.org/abs/2309.17080) / [DriveDreamer](https://arxiv.org/abs/2309.09777)
<a id="paper-18-drivegenvlm"></a>

#### DriveGenVLM

- **Title / 标题**：DriveGenVLM: Real-world Video Generation for Vision-Language Models in Autonomous Driving
- **Year / 年份**：2024
- **Core Contribution / 核心贡献**：用生成驾驶视频辅助视觉语言理解。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2408.16647)
<a id="paper-18-world-models-for-autonomous-driving-survey"></a>

#### World Models for Autonomous Driving Survey

- **Title / 标题**：World Models for Autonomous Driving: An Initial Survey
- **Year / 年份**：2025
- **Core Contribution / 核心贡献**：将驾驶世界模型分为场景生成、预测、规划交互等方向。
- **Links / 链接**：[Paper](https://arxiv.org/abs/2501.11260)
<a id="paper-18-nerf-3dgs"></a>

#### NeRF / 3DGS

- **Title / 标题**：NeRF: Representing Scenes as Neural Radiance Fields for View Synthesis / 3D Gaussian Splatting for Real-Time Radiance Field Rendering
- **Year / 年份**：2020 / 2023
- **Core Contribution / 核心贡献**：为数字孪生和闭环仿真提供三维视觉基础。
- **Links / 链接**：[NeRF](https://arxiv.org/abs/2003.08934) / [3DGS](https://arxiv.org/abs/2308.04079)
<a id="paper-18-habitat-isaac-sim-carla-nuplan"></a>

#### Habitat / Isaac Sim / CARLA / nuPlan

- **Title / 标题**：Habitat / Isaac Sim / CARLA / nuPlan
- **Year / 年份**：2017–2022
- **Core Contribution / 核心贡献**：具身、驾驶、机器人系统评估的重要基础设施。
- **Links / 链接**：[Habitat](https://arxiv.org/abs/1904.01201) / [CARLA](https://arxiv.org/abs/1711.03938) / [nuPlan](https://arxiv.org/abs/2106.11810) / [Isaac Sim](https://developer.nvidia.com/isaac/sim)
</details>
