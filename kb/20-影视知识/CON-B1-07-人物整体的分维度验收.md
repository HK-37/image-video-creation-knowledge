---
title: 人物整体的分维度验收
created: 2026-11-16
tags: [B1, 人物呈现, 身份外观连续性, 表演动作视线, 分维验收, 素材筛选]
source: "https://openaccess.thecvf.com/content/CVPR2025/html/Hu_PersonaHOI_Effortlessly_Improving_Face_Personalization_in_Human-Object_Interaction_Generation_CVPR_2025_paper.html; https://openaccess.thecvf.com/content/WACV2023/html/Agarwal_FaceOff_A_Video-to-Video_Face_Swapping_System_WACV_2023_paper.html; https://openaccess.thecvf.com/content/CVPR2023/html/Ye_Affordance_Diffusion_Synthesizing_Hand-Object_Interactions_CVPR_2023_paper.html; ../../人物呈现专题-一手源证据汇编.md; ../../框架V1.1-专业依据与AI创作应用.md"
status: 未验证
type: con
id: CON-B1-07
domain: B1-人物呈现与视觉身份/身份与外观连续性; B1-人物呈现与视觉身份/表演动作与视线
evidence-level: E1
scope: 项目内（验收方法未实测）
---

# 人物整体的分维度验收

## 来源命题

PersonaHOI（CVPR 2025）指出，面部个性化可能以 full-body coherence 为代价；FaceOff（WACV 2023）将 identity、expression、pose、background 等分列处理；Affordance Diffusion（CVPR 2023）将交互布局与内容分开。它们共同提示：面部、身份、身体与交互不是可以相互替代的单一指标。

- Hu 等，PersonaHOI：https://openaccess.thecvf.com/content/CVPR2025/html/Hu_PersonaHOI_Effortlessly_Improving_Face_Personalization_in_Human-Object_Interaction_Generation_CVPR_2025_paper.html
- Agarwal 等，FaceOff：https://openaccess.thecvf.com/content/WACV2023/html/Agarwal_FaceOff_A_Video-to-Video_Face_Swapping_System_WACV_2023_paper.html
- Ye 等，Affordance Diffusion：https://openaccess.thecvf.com/content/CVPR2023/html/Ye_Affordance_Diffusion_Synthesizing_Hand-Object_Interactions_CVPR_2023_paper.html

「每轮核心目标 + 分维三态记录 + 核心失败不可抵消」是本项目的素材验收方法，受框架 V1.1 的 C2 要求约束；不是上述论文共同发布的行业标准或评分体系。

## 项目转译

每轮先写核心目标和不可妥协项，再按任务需要检查身份、表面修饰、表情、姿态/身体结构、接触/遮挡、服化、时序稳定与输入可行性。每项记录 `通过 / 失败 / 无法判定`，附对应可见部位或时间段及返工原因；无关维度标 `不适用`，不为了填满表格而检查。

核心接触失败时，不用脸美或脸像抵消；动作成立而身份不符时，不能称为同一人物的合格版本。局部改善与整体可用性分别记录，具体维度的优先级由任务决定，不设置通用总分。

## 可观察验收

- **通过**：本轮核心项及所有必要维度均有可观察的通过依据；没有未解决的核心失败；允许存在的偏差已明确记录，且视频的必要时间段而非只有最佳帧被检查。
- **失败**：任一核心项失败，例如关键接触错位、身份漂移、身体结构错误、必要动作/时序不成立；即使其他维度改善也不判整镜通过。不能以「画质好」「工具已执行」替代观察。
- **无法判定**：关键部位、时间段、参考或输入记录不足，不能得出该维度结论；它不能被当作通过。须补齐可比素材或改变检查条件，再决定是否返工。

## 不适用条件

- **不能推出**：多个论文的模块可直接组成任意模型通用的生产流水线，或一次合格可证明长期成功率、跨模型稳定性。维度多不等于必须平均权重或计算总分。
- **结论边界**：维度权重和核心否决项依任务而定；单次、单人素材不能外推普遍效果。本条为项目内未实测的验收方案；独立人物专题复核已于 2026-11-18 完成并通过，项目实测仍未完成。

## 关联

- [[CON-B1-01-表面修图与几何改变]]：记录纹理、色调与几何的分别结果。
- [[CON-B1-02-身份与可变属性]]：核对身份锚点及跨时间漂移。
- [[CON-B1-03-行动目标与身体行为]]：核对行动及身体行为是否可读。
- [[CON-B1-04-表情的强度与时间过程]]：核对表情通道与视频时序。
- [[CON-B1-05-姿态表情与身份的分维控制]]：核对全身结构，避免以脸部替代整体。
- [[CON-B1-06-接触姿态与前后遮挡]]：核对局部接触和前后关系，核心失败不被抵消。
- [[REG-知识库规范]]：遵循证据、项目转译与验证状态的分层规则。
