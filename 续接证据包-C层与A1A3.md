# 续接证据包：C 层与 A1/A3

- 日期：2026-11-16
- 来源：research-ai-delivery 已交付的调研与中间成果，由主理人固化。
- 用途：供后续小批量建库使用；不是项目实测，不证明 C 层或 A1/A3 已建成。

## C 层：7 个已调研概念

### 1. 条件输入职责与限制

- ControlNet 在特定扩散模型研究中加入边缘、深度、分割、姿态等空间条件；不证明逐像素满足条件，也不证明任意商业模型通用。
  https://openaccess.thecvf.com/content/ICCV2023/html/Zhang_Adding_Conditional_Control_to_Text-to-Image_Diffusion_Models_ICCV_2023_paper.html
- LDM 的 cross-attention 可接入文本、框等条件，限于其研究架构。
  https://openaccess.thecvf.com/content/CVPR2022/html/Rombach_High-Resolution_Image_Synthesis_With_Latent_Diffusion_Models_CVPR_2022_paper.html
- Gemini Omni 官方能力绑定当前模型、接口、区域和日期，不能外推为长期或其他模型事实。
  https://aistudio.google.com/docs/omni
- 项目转译：分别登记文本、参考图、首/尾帧、姿态、深度等条件的职责，先小样验证；条件提交不等于保真，技术可控不等于美学正确。

### 2. 身份与空间保真

- Google 官方图像生成示例涉及多图复合、角色一致性与姿态参考，但官方建议不是跨镜、跨姿态保证。
  https://aistudio.google.com/docs/image-generation
- ControlNet 同上，空间条件不等于物理空间正确。
- 项目转译：身份与空间分别验收；身份检查面部/发型/服饰/道具/左右与尺度，空间检查锚点/层次/透视/接触/阴影；按角度、姿态、遮挡前后逐镜核对，不能用单张最佳帧代替。

### 3. 动作、遮挡与时序保真

- Motion Representations 研究专门表示驱动运动，不证明通用模型会准确执行。
  https://openaccess.thecvf.com/content/CVPR2021/html/Siarohin_Motion_Representations_for_Articulated_Animation_CVPR_2021_paper.html
- Align Your Latents、Tune-A-Video 分别显示逐帧质量与时间一致/时空注意是不同技术问题。
  https://openaccess.thecvf.com/content/CVPR2023/html/Blattmann_Align_Your_Latents_High-Resolution_Video_Synthesis_With_Latent_Diffusion_Models_CVPR_2023_paper.html
  https://openaccess.thecvf.com/content/ICCV2023/html/Wu_Tune-A-Video_One-Shot_Tuning_of_Image_Diffusion_Models_for_Text-to-Video_Generation_ICCV_2023_paper.html
- AMT 表明大运动和遮挡插帧需要专门处理，不能把插帧平滑当时序保真。
  https://openaccess.thecvf.com/content/CVPR2023/html/Li_AMT_All-Pairs_Multi-Field_Transforms_for_Efficient_Frame_Interpolation_CVPR_2023_paper.html
- Omni 限制页提示扩展输入的上下文限制，不能宣称长时身份/时序自动保持。
  https://aistudio.google.com/docs/omni#limitations
- 项目转译：动作轨迹、遮挡前中后、全段时序分别验；不能只比较首尾帧或单帧。

### 4. 分维度素材验收

- ITU-R BT.500-15 规范主观图像质量评价的方法、尺度与观看条件，不是 AI 身份一致性或审美正确标准。
  https://www.itu.int/rec/R-REC-BT.500-15-202305-I/en
- 项目转译：技术完整性、条件与保真、创作适配三栏独立结论；记录版本、设备、环境、维度、复核人和时间码；高分辨率不能抵消错脸/错动作。

### 5. 生成素材与技术合成

- After Effects 官方资料把透明、蒙版、mattes、keying、图层合成列为独立技术处理。
  https://helpx.adobe.com/after-effects/desktop/work-with-transparency-and-compositing/compositing-in-after-effects/compositing-transparency-overview-resources.html
  https://helpx.adobe.com/after-effects/using/alpha-channels-masks-mattes.html
- 项目转译：生成输出只是素材；透明度、图层、跟踪、边缘、接触阴影、局部修补需独立验收；生成像成片不等于有可编辑分层或干净 alpha。

### 6. 调色、编码与交付

- BT.709-6 规定 HDTV 制作/交换参数；BT.1886-0 是参考显示 EOTF；不能混作“套 Rec.709 LUT”或通用互联网播放规范。
  https://www.itu.int/rec/R-REC-BT.709-6-201506-I/en
  https://www.itu.int/rec/R-REC-BT.1886-0-201103-I/en
- EBU R103 是数字电视信号容差建议，不是内容审美验收。
  https://tech.ebu.ch/docs/r/r103.pdf
- 项目转译：素材验收→合成→明确色彩管理链下调色→母版→按交付规格编码→实机 QC；元数据、解码播放、输出规格分别验，标准版本逐项目确认。

### 7. 版本、成本、审核与返工

- Veo 旧版 seed 不保证确定性；模型/接口可用性会变化。
  https://aistudio.google.com/docs/veo
  https://aistudio.google.com/docs/video
- Omni 审核、区域与输入限制会变化。
  https://aistudio.google.com/docs/omni#limitations
- 价格与计费只代表对应模型、接口与查询时点。
  https://aistudio.google.com/docs/pricing
  https://aistudio.google.com/docs/interactions#billing
- 项目转译：保留模型/接口/地区/日期、提示与输入 hash、seed（如有）、输出 hash、任务/错误、后期版本、审核与费用；失败按接口/政策/保真/合成编码分类；seed 不保证复现，单次成功率不能当 SLA。

## A1/A3：中间包，非完整专题

### 已核边界

- 创作定位不等于题材/风格词；应含主体、信息、观看目的、受众/情境、形式与资源约束。
- 导演式统筹不等于包办所有部门；各专业仍有独立贡献。
- 视点不等于单一 POV 机位；风格不等于滤镜，须落实到空间、表演、光色、声音与剪辑。
- 简报不等于完整剧本或分镜；应含目标、受众、交付、输入、不可变项、验收与可行性。
- 专业事实与 AI 项目流程必须分栏。

### 5 个已读来源

1. DGA 官方摘要：导演整合创作要素，覆盖筹备/拍摄/后期；导演不等于 final cutting authority，GAI 条款限其工会语境。
   https://dga.org/Contracts/Creative-Rights/Summary---Television
2. 《Directing》6e 官方页：作者性/视点/风格、剧本、镜头语言、演员/视觉设计/拍摄稿、制作与后期。
   https://www.routledge.com/Directing-Film-Techniques-and-Aesthetics/Rabiger-Hurbis-Cherrier/p/book/9780815394310
3. 《From Screenplay to Visual Plan》：shooting script、俯视图、故事板用于沟通风格与镜头选择，不支持所有项目强制分镜。
   https://www.taylorfrancis.com/chapters/mono/10.4324/9781315815893-5/screenplay-visual-plan
4. 《The Cast and Crew》：叙事电影是协作艺术，导演为创作驱动，美术与录音有独立职责。
   https://www.taylorfrancis.com/chapters/mono/10.4324/9781315815893-7/cast-crew
5. 《Section One Review: Prep》：筹备期拆解剧本、讨论调性、决定屏幕转译并传达团队；不外推其筹备时长。
   https://www.taylorfrancis.com/chapters/mono/10.4324/9780240818740-18/section-one-review-prep

### 未完成项

- 受众差异反应、观看目标到传播/转化的可靠映射。
- 不可变项通用清单与 AI 简报模板；目前只能作为项目建议。
- 视点/风格跨教材、片种和学派的交叉验证。
- 完整概念集、可观察验收及正式知识条目。
