---
title: 身份与可变属性的分离
created: 2026-11-16
tags: [B1, 人物呈现, 身份外观连续性, 身份锚点, 可变属性]
source: "https://openaccess.thecvf.com/content_cvpr_2018/html/Bao_Towards_Open-Set_Identity_CVPR_2018_paper.html; https://openaccess.thecvf.com/content/CVPR2024/html/Peng_PortraitBooth_A_Versatile_Portrait_Model_for_Fast_Identity-preserved_Personalization_CVPR_2024_paper.html; https://openaccess.thecvf.com/content/WACV2023/html/Agarwal_FaceOff_A_Video-to-Video_Face_Swapping_System_WACV_2023_paper.html; ../../人物呈现专题-一手源证据汇编.md"
status: 未验证
type: con
id: CON-B1-02
domain: B1-人物呈现与视觉身份/身份与外观连续性
evidence-level: E1
scope: 通用（项目未实测）
---

# 身份与可变属性的分离

## 来源命题

Bao 等（CVPR 2018）区分 identity vector 与 pose、emotion、illumination、background 等属性。PortraitBooth（CVPR 2024）把身份扭曲与表情多样性作为不同问题处理；FaceOff（WACV 2023）在其视频换脸任务中分别处理 source identity/expression 与 target background/pose。三者支持在特定人脸生成/编辑任务中把身份和其他可变属性分开考察。

- Bao 等，Towards Open-Set Identity：https://openaccess.thecvf.com/content_cvpr_2018/html/Bao_Towards_Open-Set_Identity_CVPR_2018_paper.html
- Peng 等，PortraitBooth：https://openaccess.thecvf.com/content/CVPR2024/html/Peng_PortraitBooth_A_Versatile_Portrait_Model_for_Fast_Identity-preserved_Personalization_CVPR_2024_paper.html
- Agarwal 等，FaceOff：https://openaccess.thecvf.com/content/WACV2023/html/Agarwal_FaceOff_A_Video-to-Video_Face_Swapping_System_WACV_2023_paper.html

这些论文不证明任意模型都能自动解耦这些属性。下述「身份锚点/允许改变项登记表」和人工对照顺序属于项目转译。

## 项目转译

先提供参考人物或角色设定，再列出本轮应保持的身份锚点，例如相近角度下的脸型、眼鼻口相对关系及其他稳定辨识特征；另列允许变化的姿态、表情、光线、背景、服化等属性。每轮只改变任务需要的属性，不把「同一人」「一模一样」等纯文字当作身份已保持的视觉证据。

对视频或跨镜素材，除单帧身份外，记录要检查的时间段和镜头切换点；不要用某个最佳帧替代连续性检查。

## 可观察验收

- **通过**：在参考与结果角度、表情和遮挡可比时，约定的脸型、眼鼻口相对关系及稳定特征保持一致；允许改变的属性按任务变化，未授权属性没有可辨漂移。视频还须连续检查跨时间/跨镜，而非只核对首帧。
- **失败**：姿态、表情或光线改变时，稳定身份特征同步发生非预期改变；或视频后段/另一镜头中身份锚点漂移。动作或背景符合要求不能抵消身份失败。
- **无法判定**：缺少参考，或参考与结果的角度、清晰度、遮挡差异使关键锚点不可比较；此时最多记录本次角色外观是否自洽，不能断言与现实人物相同。

## 不适用条件

- **不能推出**：论文所述模型/任务的身份与属性分离能力可直接迁移到任意生成工具；也不能由人工相似判断推出统一身份评分阈值。
- **结论边界**：无现实人物参考时，只能检查当前角色的一致性，不能证明与现实人物同一。角度、遮挡和光照会限制人工核验；本条不代替独立身份识别评估或项目实测。

## 关联

- [[CON-B1-01-表面修图与几何改变]]：修图与几何改变须服从身份锚点，而非只追求表面美化。
- [[CON-B1-04-表情的强度与时间过程]]：表情变化须与身份漂移分开观察。
- [[CON-B1-05-姿态表情与身份的分维控制]]：姿态条件成立后，身份仍需另行验收。
- [[CON-B1-07-人物整体的分维度验收]]：身份是整体素材验收的独立核心维度。
