---
title: 表情的强度与时间过程
created: 2026-11-16
tags: [B1, 人物呈现, 表演动作视线, 表情, 时序, 视线]
source: "https://openaccess.thecvf.com/content/WACV2022/html/Uddin_Quantified_Facial_Expressiveness_for_Affective_Behavior_Analytics_WACV_2022_paper.html; ../../人物呈现专题-一手源证据汇编.md"
status: 未验证
type: con
id: CON-B1-04
domain: B1-人物呈现与视觉身份/表演动作与视线
evidence-level: E1
scope: 通用（项目未实测）
---

# 表情的强度与时间过程

## 来源命题

Uddin 与 Canavan（WACV 2022）在其 facial expressiveness 研究中使用 AUs、landmarks、head pose、gaze 以及 frame-level temporal changes 等可见/可测特征描述表情表现。这支持把面部表现拆成多个可观察通道，并在视频中检查逐帧时间变化。

- Uddin & Canavan，Quantified Facial Expressiveness for Affective Behavior Analytics：https://openaccess.thecvf.com/content/WACV2022/html/Uddin_Quantified_Facial_Expressiveness_for_Affective_Behavior_Analytics_WACV_2022_paper.html

来源不支持从 AU、视线或头姿唯一推断真实内心情绪。以下用自然语言记录起止状态、变化与保持，是本项目的创作和验收转译，不是论文规定的提示词格式或通用表情量表。

## 项目转译

视频描述选定段落的起始面部状态、发生变化的触发或情境、目标表情、变化快慢、保持或结束方式，并同时记录必要的头姿和视线变化。用眉眼、嘴部等可见部位的相对变化说明强弱，不虚构跨模型通用的强度数值。

静态图只描述一个选定瞬间的眉眼、嘴部、头姿与视线，不借单帧声称已表达完整变化过程。表情是人物行动的一部分，但不以情绪词单独替代可见行为。

## 可观察验收

- **通过**：静态图中，选定的眉眼、嘴部、头姿和视线状态可见且彼此不冲突。视频中，起止状态、变化发生的时段、相对强弱、速度及保持/结束符合任务描述，全过程无未授权突跳或变成另一套表演。
- **失败**：关键部位不可见却宣称表情完成；视频变化时机、保持或结束偏离任务，出现明显突跳、非预期反复或强度失控；仅首尾帧符合而中段不符，仍判时序失败。
- **无法判定**：单帧无法证明完整动作过程；帧率、时长、清晰度、脸部尺寸或遮挡不足以分辨变化时，只能记录可见片段，不能补写中间过程或判断内心状态。

## 不适用条件

- **不能推出**：AU、视线、头姿或某种表情必然代表某种真实内心情绪或固定观众体验；也不能设一个适用所有人物、模型和情境的表情强度值。
- **结论边界**：论文的任务与指标不能自动转为任意视频模型的可控能力。本条只处理可见表现与时间过程，不代替身份稳定性或身体接触检查，且尚未完成项目实测。

## 关联

- [[CON-B1-02-身份与可变属性]]：检查表情变化时须区分表演变化与身份漂移。
- [[CON-B1-03-行动目标与身体行为]]：表情、视线应与当前行动及身体行为协调。
- [[CON-B1-07-人物整体的分维度验收]]：时序稳定是独立验收维度，单张最佳帧不能抵消过程失败。
