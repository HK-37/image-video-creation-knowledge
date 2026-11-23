---
title: 画幅、比例、取景与画外证据
created: 2026-11-16
tags: [B2, 摄影构图空间, 画幅, 比例, 取景, 画外]
source: "https://www.taylorfrancis.com/chapters/mono/10.4324/9781003120889-2/composing-frame; https://www.taylorfrancis.com/books/9781136043468/chapters/10.4324/9780080551692-8; https://openaccess.thecvf.com/content_cvpr_2016/html/Mai_Composition-Preserving_Deep_Photo_CVPR_2016_paper.html; ../../框架V1.1-专业依据与AI创作应用.md"
status: 未验证
type: con
id: CON-B2-01
domain: B2-摄影构图与空间组织/画幅与取景
evidence-level: E3
scope: 通用（项目未实测）
---

# 画幅、比例、取景与画外证据

## 来源命题

Roberts-Breslin《Composing the Frame》摘要把 frame 解释为决定看见/听见什么以及画外暗示的边界，矩形边的比例为 aspect ratio；取景还包括主体在画面中的大小和显示多少。Block《Space》摘要将空间分为 deep、flat、limited、ambiguous，并另列 aspect ratio、surface divisions、open/closed space，支持画幅与空间组织关联而非只有一个比例名称。

- Roberts-Breslin：https://www.taylorfrancis.com/chapters/mono/10.4324/9781003120889-2/composing-frame
- Block：《Space》：https://www.taylorfrancis.com/books/9781136043468/chapters/10.4324/9780080551692-8

Mai、Jin、Liu（CVPR 2016）的论文处理照片美学评估模型输入问题：裁剪、缩放、padding 可能损害构图、降低分辨率或造成变形，其方法直接处理原始尺寸/比例的图像，并在 AVA 基准上评估。这是特定美学评估模型的技术证据，不是任意生图模型能保持构图或自动安全裁切的证明。

- Mai 等：https://openaccess.thecvf.com/content_cvpr_2016/html/Mai_Composition-Preserving_Deep_Photo_CVPR_2016_paper.html

## 项目转译

先登记交付比例、主体与必要文字/标识的安全范围、动作或接触点、必须保留的画外暗示，再决定重新取景或改画幅。改比例时比较同一参考与结果的主体可见范围、边缘切断、文字完整性及前后遮挡；不能为填满新画幅而强行裁掉核心证据。

安全区是项目内按内容和交付渠道标出的检查区域，不是统一百分数。画外内容可作为叙事暗示，但不能把不可见的关键物件/接触当作已清楚呈现。

## 可观察验收

- **通过**：目标比例正确；主体、必要文字、关键动作/接触点位于各自预定安全范围，边缘无不合理切断；画内证据与预期画外暗示一致，未因改画幅改变关键空间关系。
- **失败**：拉伸/压缩导致主体变形，关键文字或接触点被裁掉，主体可见范围或画外关系违背任务；只满足输出尺寸而丢失叙事证据。
- **无法判定**：缺少原图、目标渠道要求或局部细节不足时，不能判断裁切是否损害内容；画外事件无法仅凭画幅选择证明已经发生。

## 不适用条件

- **不能推出**：某一比例天然更高级或更有情绪，改画幅必然能保持构图，或论文中的美学评估网络可直接当任意生成工具的裁切能力。
- **结论边界**：安全区与保留项依任务确定；来源不提供通用安全区数值或改画幅公式。本条为未实测的项目转译，模型能力须另按版本与输入核验。

## 关联

- [[CON-B2-02-景别与机位]]：画幅改变后分别检查主体可见范围与观察位置。
- [[CON-B2-03-站位遮挡与纵深]]：裁切可能改变遮挡、前后关系和空间类型。
- [[CON-B2-08-空间叙事与连续性]]：跨镜改比例仍需保留行动与空间证据。
- [[CON-A4-06-单镜多镜验收与最终剪辑]]：改画幅后的真实素材须完整检查，不只看计划。
- [[CON-B1-06-接触姿态与前后遮挡]]：接触点属于不可轻易裁掉的核心证据。
