---
title: 曝光与光度、色调计量
created: 2026-11-16
tags: [B3, 曝光, 光度计量, 色调, 示波, 光通量, 照度, 亮度]
source: "https://www.taylorfrancis.com/chapters/mono/10.4324/9781003355137-21/fundamentals-lighting-light-metering-exposure; https://cie.co.at/eilvterm/17-21-039; https://cie.co.at/eilvterm/17-21-060; https://cie.co.at/eilvterm/17-21-050; https://www.taylorfrancis.com/chapters/mono/10.4324/9781003120889-5/light; ../../框架V1.1-专业依据与AI创作应用.md"
status: 未验证
type: con
id: CON-B3-03
domain: B3-光影色彩与影调氛围/曝光与光度计量
evidence-level: E3
scope: 通用（项目未实测）
---

# 曝光与光度、色调计量

## 来源命题

Routledge《Fundamentals of Lighting, Light Metering and Exposure》分别讨论入射/点测光、波形/矢量示波、不同曝光方法和 HDR，支持按主体、成像和显示链路判断曝光，而不是统一追求更亮。

- 教材章节：https://www.taylorfrancis.com/chapters/mono/10.4324/9781003355137-21/fundamentals-lighting-light-metering-exposure

CIE 将 luminous flux（光通量）的单位规定为 lumen（lm），illuminance（照度）为表面入射光通量密度、单位 lux，luminance（亮度）为指定方向和位置的光强相对投影面积、单位 cd/m²。三者均不能直接当作画面曝光值。

- 光通量：https://cie.co.at/eilvterm/17-21-039
- 照度：https://cie.co.at/eilvterm/17-21-060
- 亮度：https://cie.co.at/eilvterm/17-21-050

《Making Media》入门摘要把 quantity 泛称 lumens 并连到曝光，容易混淆光通量、照度、亮度与曝光；需要精确计量时以 CIE 的量纲定义为裁决依据，不沿用该简化说法。

- 教材对照：https://www.taylorfrancis.com/chapters/mono/10.4324/9781003120889-5/light

## 项目转译

先记录需要保护的关键肤色、产品、文字或环境细节，以及允许失去细节的区域，再记录输入编码、监看/输出变换和示波读取位置。高调/低调只描述明暗分布，不当作曝光补偿值。

实物布光可分别登记光源 lm、主体位置 lux、反射/显示方向 cd/m²；AI 文本输入不虚构这些物理读数。对生成素材只读取实际文件和显示链路，不反推模型内部存在相同灯具或曝光参数。没有统一肤色 IRE 或统一脸部明度默认值。

## 可观察验收

- **通过**：关键细节可读，非预期削波或暗部压死已识别；示波数值有采样区域、信号编码和监看/输出条件，引用量纲与对象一致；实际输出而非提示词参与验收。
- **失败**：把灯具 lm、主体照度或显示亮度直接当画面曝光；把高调等同过曝、低调等同欠曝；不说明 Log/SDR/HDR 或变换就引用数字；把色温 K 当亮度。
- **无法判定**：未知输入/输出变换、显示条件或关键区域不可见；只有屏幕截图而没有原文件/示波条件时，不作精确光度或曝光结论。

## 不适用条件

- **不能推出**：存在跨模型通用曝光词、IRE、肤色明度或光度阈值；数字合格即可证明纹理、身份、色彩外观或审美合格。
- **结论边界**：本条支持计量对象与画面判断分离，不替代设备/软件具体文档。AI 图像中无法核验的物理量应标无法判定，而非从视觉外观反推。

## 关联

- [[CON-B3-02-光比明暗分配与影调]]：光比和影调是画面组织，不等于曝光或光度量纲。
- [[CON-B3-04-CCT色彩计量与颜色外观]]：色温计量不与曝光或明暗混淆。
- [[CON-B3-05-颜色管理与创作调色分账]]：曝光/示波读数必须放入输入输出变换语境。
- [[CON-B3-08-跨镜光色一致性]]：用相同技术条件比较镜间曝光和关键细节。
- [[CON-B1-07-人物整体的分维度验收]]：人物肤色和结构不可被统一曝光数值代替。
- [[REG-知识库规范]]：技术测量不越界为审美规则。
