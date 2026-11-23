---
title: 接触、姿态与前后遮挡
created: 2026-11-16
tags: [B1, 人物呈现, 表演动作视线, 接触, 遮挡, 手物交互]
source: "https://openaccess.thecvf.com/content/CVPR2023/html/Ye_Affordance_Diffusion_Synthesizing_Hand-Object_Interactions_CVPR_2023_paper.html; https://openaccess.thecvf.com/content/CVPR2025/html/Hu_PersonaHOI_Effortlessly_Improving_Face_Personalization_in_Human-Object_Interaction_Generation_CVPR_2025_paper.html; ../../人物呈现专题-一手源证据汇编.md"
status: 未验证
type: con
id: CON-B1-06
domain: B1-人物呈现与视觉身份/表演动作与视线
evidence-level: E1
scope: 通用（项目未实测）
---

# 接触、姿态与前后遮挡

## 来源命题

Affordance Diffusion（CVPR 2023）将手物交互分为 LayoutNet（where/layout）与 ContentNet（how/content），并预测 hand articulation 与 approaching orientation。PersonaHOI（CVPR 2025）区分脸部个性化与非面部交互区域，支持在人物—物件生成中分别关注脸部和交互区域。

- Ye 等，Affordance Diffusion：https://openaccess.thecvf.com/content/CVPR2023/html/Ye_Affordance_Diffusion_Synthesizing_Hand-Object_Interactions_CVPR_2023_paper.html
- Hu 等，PersonaHOI：https://openaccess.thecvf.com/content/CVPR2025/html/Hu_PersonaHOI_Effortlessly_Improving_Face_Personalization_in_Human-Object_Interaction_Generation_CVPR_2025_paper.html

本条只采用已核论文页支持的布局/内容、手部姿态与接近方向，以及面部/交互区域的区分。更细的碰撞、受力、遮挡物理论文规则尚未逐页复核，不在本条写成事实。

## 项目转译

不只写「握住」「伸进」「贴住」，而写清交互对象及被接触的功能部位、手或身体的接近方向、手/指或其他接触部位的姿态，以及谁遮谁的预期前后关系。需要时补充接触处的可见材质、光影或形变目标，但不虚构统一物理公式。

生成后把接触处作为独立局部核验对象。视频分别描述接触建立、保持、解除的阶段；插入孔洞或缝隙时，额外记录孔缘与插入部位的覆盖关系。措辞本身不是接触成立的证据。

## 可观察验收

- **通过**：接触发生在指定功能部位；手指/手掌或其他接触部位姿态、比例和透视可辨且符合任务；前后遮挡与预定关系一致，接触处光影、材质和形变无可见矛盾。视频中的建立、保持、解除顺序可见且无未授权穿脱或跳变。
- **失败**：对象或部位错误、悬空/错位、非预期穿透，手部姿态或比例异常；遮挡关系反转、孔缘覆盖错误，或视频接触尚未建立便已保持、未解除便突然分离。脸部美观不能抵消接触失败。
- **无法判定**：远景、运动模糊、分辨率或遮挡使接触点、孔缘和前后关系不可见；不能凭整图印象判成功，应标为无法判定并调整素材或检查视图，而非推断物理关系。

## 不适用条件

- **不能推出**：上述论文能给出任意模型通用的接触提示词公式，或自然语言能保证碰撞、受力、遮挡都物理正确。人脸个性化与交互区域分开关注不等于两者已被模型完美协调。
- **结论边界**：关于碰撞、受力与遮挡的更细物理规则仍待原文复核；本条只作可观察关系核验，不宣称物理仿真。独立人物专题复核已于 2026-11-18 完成并通过；项目实测仍未完成。

## 关联

- [[CON-B1-03-行动目标与身体行为]]：接触姿态要服务行动目标，避免孤立的「正确手势」。
- [[CON-B1-05-姿态表情与身份的分维控制]]：先保证身体结构可辨，再检查接触；脸部身份与交互区域不可互替。
- [[CON-B1-04-表情的强度与时间过程]]：动态交互还需检查接触过程，不能只看首尾状态。
- [[CON-B1-07-人物整体的分维度验收]]：核心接触失败是独立否决依据，不被其他维度抵消。
