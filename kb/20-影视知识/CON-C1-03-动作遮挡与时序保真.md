---
title: 动作遮挡与时序保真
created: 2026-11-16
tags: [C1, AI技术控制, 动作保真, 遮挡, 时序一致性, 插帧, 视频扩散, 全段验收]
source: "https://openaccess.thecvf.com/content/CVPR2021/html/Siarohin_Motion_Representations_for_Articulated_Animation_CVPR_2021_paper.html; https://openaccess.thecvf.com/content/CVPR2023/html/Blattmann_Align_Your_Latents_High-Resolution_Video_Synthesis_With_Latent_Diffusion_Models_CVPR_2023_paper.html; https://openaccess.thecvf.com/content/ICCV2023/html/Wu_Tune-A-Video_One-Shot_Tuning_of_Image_Diffusion_Models_for_Text-to-Video_Generation_ICCV_2023_paper.html; https://openaccess.thecvf.com/content/CVPR2023/html/Li_AMT_All-Pairs_Multi-Field_Transforms_for_Efficient_Frame_Interpolation_CVPR_2023_paper.html; https://aistudio.google.com/docs/omni#limitations; ../../续接证据包-C层与A1A3.md; ../../框架V1.1-专业依据与AI创作应用.md"
status: 未验证
type: con
id: CON-C1-03
domain: C1-AI技术控制与交付/动作遮挡与时序保真
evidence-level: E3
scope: 项目内（通用来源，项目未实测）
---

# 动作遮挡与时序保真

## 来源命题

Motion Representations for Articulated Animation（CVPR 2021）提出用专门的运动表示来驱动关节化对象动画。该工作支持「运动需要专门表示」这一命题，其实验限于自身模型与数据，不证明任意通用视频生成模型能准确执行给定动作。

- Motion Representations：https://openaccess.thecvf.com/content/CVPR2021/html/Siarohin_Motion_Representations_for_Articulated_Animation_CVPR_2021_paper.html

Align Your Latents（CVPR 2023）与 Tune-A-Video（ICCV 2023）分别在视频扩散与单视频微调设定下处理时间维度：前者通过对齐时序层把图像扩散扩展到视频，后者通过时空注意微调让图像模型生成视频。二者共同支持「逐帧质量」与「时间一致性」是不同技术问题，但都限于各自研究架构与任务。

- Align Your Latents：https://openaccess.thecvf.com/content/CVPR2023/html/Blattmann_Align_Your_Latents_High-Resolution_Video_Synthesis_With_Latent_Diffusion_Models_CVPR_2023_paper.html
- Tune-A-Video：https://openaccess.thecvf.com/content/ICCV2023/html/Wu_Tune-A-Video_One-Shot_Tuning_of_Image_Diffusion_Models_for_Text-to-Video_Generation_ICCV_2023_paper.html

AMT（CVPR 2023）针对大运动与遮挡场景的插帧提出全对多场变换，说明插帧需要专门处理运动与遮挡；插帧结果平滑不等于动作或遮挡保真。

- AMT：https://openaccess.thecvf.com/content/CVPR2023/html/Li_AMT_All-Pairs_Multi-Field_Transforms_for_Efficient_Frame_Interpolation_CVPR_2023_paper.html

Gemini Omni 限制页标注了扩展输入的上下文限制，不能据此宣称长时身份或时序可自动保持。

- Omni limitations：https://aistudio.google.com/docs/omni#limitations

综合以上来源：动作轨迹、遮挡前后、全段时序是相互独立的验收维度；单帧画质、首尾帧对照、插帧平滑都不能单独代表全段时序保真。

## 项目转译

针对本项目 AI 生视频，把动作、遮挡、时序分栏验收，每栏独立给结论，不以单张最佳帧或首尾帧对照代替全段判断。

- **动作轨迹栏**：以参考视频/动作描述为基准，记录起点、关键姿态点、转折点、终点的关节位置与身体方向；比较输出帧与参考在同样时间点的轨迹是否一致；识别被替换/省略/反向的动作段。
- **遮挡前中后栏**：标注遮挡开始帧、遮挡中帧、遮挡结束帧；分别核对身体/道具在遮挡前的姿态与位置、遮挡中的可见部分、遮挡后是否回到相容状态；不假设遮挡中被遮部分仍按原轨迹运动。
- **全段时序栏**：标注镜头时间码与帧率；按均匀抽样或按创作节拍抽样比对整段，覆盖镜头前 1/4、中 1/2、后 1/4；记录身份、服装、道具、光源方向在整段内的漂移；插帧片段单独标注，与原生成帧分开判。

三栏独立记录通过/失败/无法判定。任一栏失败都不能被另外两栏通过抵消。

## 可观察验收

- **通过**：三栏均给出独立结论；动作轨迹有逐关键点的输入/输出对照；遮挡前中后均有对应帧；全段时序覆盖镜头前中后抽样点；插帧片段单独标注；任一漂移或动作偏离有显式标注。
- **失败**：只对照首尾帧或单张最佳帧就宣称全段通过；用插帧平滑当作动作/遮挡保真证据；用整体画质或「看起来像」替代逐栏核验；三栏中任一栏缺失结论。
- **无法判定**：缺少遮挡中或关键动作点的输出帧；缺少参考视频或对应时间码；输出被裁切/压缩/后期到无法比对关节位置或遮挡细节。

## 不适用条件

- **不能推出**：Motion Representations / Align Your Latents / Tune-A-Video / AMT 的方法可被任意商业视频生成模型直接采用；插帧平滑等于动作或遮挡保真；首尾帧一致等于全段时序一致；Omni 当前文档的上下文限制在未来版本同样适用；逐帧画质高即可代表时序保真。
- **结论边界**：本条只规范「动作/遮挡/时序」三栏的独立验收方法，不规定具体动作模板、不替代 B1 表情动作与 B2 运镜的创作判断、不预设商业模型对长时或复杂遮挡的能力。所有结论以本项目实际输入/输出对帧为准。

## 关联

- [[CON-C1-01-条件输入职责与限制]]：动作/遮挡/时序条件的提交不等于保真。
- [[CON-C1-02-身份与空间保真]]：身份与空间在遮挡前中后、动作过程中的漂移分别在两栏核验。
- [[CON-B1-03-行动目标与身体行为]]：动作轨迹栏的身体行为需对齐 B1 行动目标。
- [[CON-B1-04-表情的强度与时间过程]]：表情的时间过程与动作轨迹并行验收。
- [[CON-B1-06-接触姿态与前后遮挡]]：遮挡前中后栏对应 B1 接触与遮挡判断。
- [[CON-B2-07-运镜与对象运动]]：运镜与对象运动的创作判断独立于时序技术保真。
- [[CON-B5-04-动作切点与可剪性]]：可剪性依赖动作轨迹在切点前后的连续性。
- [[CON-B6-07-声画同步错位与视点]]：声画同步依赖动作与声音在同一时间码上的对齐。
- [[REG-知识库规范]]：来源能力、模型实际表现、项目实测分层记录。
