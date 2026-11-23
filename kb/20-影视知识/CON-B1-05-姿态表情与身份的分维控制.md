---
title: 姿态、表情与身份的分维控制
created: 2026-11-16
tags: [B1, 人物呈现, 身份外观连续性, 表演动作视线, 姿态, 分维控制]
source: "https://openaccess.thecvf.com/content/ICCV2023/html/Zhang_Adding_Conditional_Control_to_Text-to-Image_Diffusion_Models_ICCV_2023_paper.html; https://openaccess.thecvf.com/content_cvpr_2018/html/Bao_Towards_Open-Set_Identity_CVPR_2018_paper.html; https://openaccess.thecvf.com/content/CVPR2024/html/Peng_PortraitBooth_A_Versatile_Portrait_Model_for_Fast_Identity-preserved_Personalization_CVPR_2024_paper.html; https://openaccess.thecvf.com/content/CVPR2025/html/Hu_PersonaHOI_Effortlessly_Improving_Face_Personalization_in_Human-Object_Interaction_Generation_CVPR_2025_paper.html; ../../人物呈现专题-一手源证据汇编.md"
status: 未验证
type: con
id: CON-B1-05
domain: B1-人物呈现与视觉身份/身份与外观连续性; B1-人物呈现与视觉身份/表演动作与视线
evidence-level: E1
scope: 通用（项目未实测）
---

# 姿态、表情与身份的分维控制

## 来源命题

ControlNet（ICCV 2023）在其研究设置中支持 edges、depth、segmentation、human pose 等空间条件。Bao（CVPR 2018）与 PortraitBooth（CVPR 2024）分别将身份同姿态、表情等属性区分处理。PersonaHOI（CVPR 2025）指出，过度强调面部个性化可能牺牲 full-body coherence。

- Zhang 等，ControlNet：https://openaccess.thecvf.com/content/ICCV2023/html/Zhang_Adding_Conditional_Control_to_Text-to-Image_Diffusion_Models_ICCV_2023_paper.html
- Bao 等，Towards Open-Set Identity：https://openaccess.thecvf.com/content_cvpr_2018/html/Bao_Towards_Open-Set_Identity_CVPR_2018_paper.html
- Peng 等，PortraitBooth：https://openaccess.thecvf.com/content/CVPR2024/html/Peng_PortraitBooth_A_Versatile_Portrait_Model_for_Fast_Identity-preserved_Personalization_CVPR_2024_paper.html
- Hu 等，PersonaHOI：https://openaccess.thecvf.com/content/CVPR2025/html/Hu_PersonaHOI_Effortlessly_Improving_Face_Personalization_in_Human-Object_Interaction_Generation_CVPR_2025_paper.html

这些论文分别属于条件控制、人脸表示/个性化和人物—物件交互等任务，不能拼成任意模型通用的工作流。以下先身体结构、再身份与交互的检查次序是项目转译。

## 项目转译

若当前工具确有姿态、深度等条件输入，可将其作为候选控制方式，并按具体工具的官方说明检查兼容条件；本条不提供接口或参数承诺。无论是否使用条件输入，文本中仍写清左右侧、身体朝向以及头颈、肩、肘、腕、髋、膝的关键关系。

验收先看姿态和身体结构是否成立，再分别检查脸部身份、表情与整体协调。不能因脸部更像就忽略肢体比例或交互失败，也不能因姿态条件已提供就默认结果正确。

## 可观察验收

- **通过**：左右方向、身体朝向和头颈、肩、肘、腕、髋、膝连接关系符合任务；可见身体比例无异常；随后独立核验的身份、表情和交互也分别满足要求。
- **失败**：关节连接、左右关系、身体朝向或比例出现非预期错误；或姿态成立但身份改变、表情不符、身体与画面整体不协调。任一核心项失败均不以另一项改善抵消。
- **无法判定**：身体被裁切、遮挡或过小，无法观察关键关节与比例；或当前输入条件与实际结果的对应记录不足，不能把姿态符合归因于某种条件输入。

## 不适用条件

- **不能推出**：提供空间条件等于模型必然遵守，或某论文中的条件类型、身份控制和全身协调在任意工具中都可用。不同论文的实验结果不能相互证明商业模型能力。
- **结论边界**：条件类型、兼容性、接口和实际效果须按具体模型/版本另行核查。本条不是接口速查，不设跨模型身份或姿态阈值；项目生成验证尚未完成。

## 关联

- [[CON-B1-02-身份与可变属性]]：姿态与表情控制之后，身份锚点仍需独立核验。
- [[CON-B1-03-行动目标与身体行为]]：关节与朝向应服务具体行动，而非只满足姿态形状。
- [[CON-B1-06-接触姿态与前后遮挡]]：姿态成立不等于接触成立，须局部检查交互。
- [[CON-B1-07-人物整体的分维度验收]]：将身份、姿态、表情和整体协调分别记录，避免脸部指标替代全身质量。
