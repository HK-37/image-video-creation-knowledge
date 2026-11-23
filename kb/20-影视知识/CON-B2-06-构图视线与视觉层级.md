---
title: 构图、视线与视觉层级
created: 2026-11-16
tags: [B2, 摄影构图空间, 构图, 视线, 视觉层级, 注意]
source: "https://www.taylorfrancis.com/chapters/mono/10.4324/9781003120889-2/composing-frame; https://www.taylorfrancis.com/chapters/chapters/edit/10.4324/9780080958958-7/visual-language; https://www.openaccess.thecvf.com/content_cvpr_2017/html/Gorji_Attentional_Push_A_CVPR_2017_paper.html; ../../框架V1.1-专业依据与AI创作应用.md"
status: 未验证
type: con
id: CON-B2-06
domain: B2-摄影构图与空间组织/注意与视觉层级
evidence-level: E3
scope: 通用（项目未实测）
---

# 构图、视线与视觉层级

## 来源命题

Roberts-Breslin《Composing the Frame》摘要讨论主体的画面重量、对称/非对称平衡、三分法，以及 movement 和 human gaze 的暗示重量与 lookspace/leadroom。它支持把人物视线与运动方向纳入构图，但不能将三分法当成唯一构图规则。

- Roberts-Breslin：https://www.taylorfrancis.com/chapters/mono/10.4324/9781003120889-2/composing-frame

Brown《Visual Language》摘要把 frame 视为有秩序的信息组织，构图与光线可共同引导观看位置与次序，传达创作者意图。该项目标不等于保证每个观众实际只有一条观看路径。

- Brown：https://www.taylorfrancis.com/chapters/chapters/edit/10.4324/9780080958958-7/visual-language

Gorji 与 Clark（CVPR 2017）提出 Attentional Push：在显著性通路外加入场景人物 gaze location 通路，结合两类信息预测社会场景的观看注意，并在特定眼动数据集上评估。它支持把人物视线当作注意信息之一，但只证明其模型、数据与任务范围内的改进，不证明任意生成图像能让所有观众看同一点。

- Gorji & Clark：https://www.openaccess.thecvf.com/content_cvpr_2017/html/Gorji_Attentional_Push_A_CVPR_2017_paper.html

## 项目转译

先写希望观众先后辨认的行动、人物、物件或文字，再组织位置、大小、明暗、色彩、清晰度、运动及人物视线等线索。检查这些线索是否相互支持或有意形成对照；不要只把主体放到三分线交点就宣称层级完成。

人物视线可留下适当方向空间，也可有意压迫/截断，取决于创作目标。AI 输出只检查可见层级与视线指向，不用「高吸引力」「电影感」替代具体信息顺序，也不保证唯一注意点。

## 可观察验收

- **通过**：任务要求的首要信息可辨，次要信息不无意抢占；位置、大小、对比、清晰、运动和视线等线索能解释预期的观看次序，人物视线方向与物件/空间关系一致。
- **失败**：关键物件/文字被无意淹没，多个线索互相冲突导致叙事重点不可辨；人物看向错误对象、视线与画外空间矛盾；只套三分法却没有任务依据。
- **无法判定**：作者无法从单张图证明观众真实注视顺序；不同受众、观看时长与任务可能改变注意，需要受众或眼动验证，不能将模型预测等同观众必然反应。

## 不适用条件

- **不能推出**：三分法适用于所有画面、视线/明暗/清晰任一因素必然决定注意，或注意力模型能证明任意生成模型能力和唯一观看路径。
- **结论边界**：教材的构图建议、项目层级清单与特定眼动模型证据分开保存；本条不设注意强度分数或情绪公式，项目实测与受众验证均未完成。

## 关联

- [[CON-B2-05-景深与焦点]]：清晰度只是注意线索之一。
- [[CON-B2-08-空间叙事与连续性]]：跨镜需注意对象和行动信息连续，而非只逐帧美观。
- [[CON-A4-05-从节拍到镜头序列]]：镜头层级由节拍功能和信息选择决定。
- [[CON-B1-03-行动目标与身体行为]]：人物视线应与行动方向一致。
- [[CON-B1-04-表情的强度与时间过程]]：视频中的视线变化需按时间核验。
