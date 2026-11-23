---
title: 生成素材与技术合成
created: 2026-11-16
tags: [C1, AI技术控制, 技术合成, 透明度, alpha, 蒙版, mattes, keying, 图层, 局部修补]
source: "https://helpx.adobe.com/after-effects/desktop/work-with-transparency-and-compositing/compositing-in-after-effects/compositing-transparency-overview-resources.html; https://helpx.adobe.com/after-effects/using/alpha-channels-masks-mattes.html; ../../续接证据包-C层与A1A3.md; ../../框架V1.1-专业依据与AI创作应用.md"
status: 未验证
type: con
id: CON-C1-05
domain: C1-AI技术控制与交付/生成素材与技术合成
evidence-level: E3
scope: 项目内（通用来源，项目未实测）
---

# 生成素材与技术合成

## 来源命题

Adobe After Effects 官方文档把 compositing/transparency 作为独立技术主题，涵盖 alpha 通道、蒙版（masks）、mattes、keying、轨道蒙版、图层混合模式、预合成等；这些是不同的技术处理路径，各有独立输入、参数与失败模式。

- Adobe 合成与透明总览：https://helpx.adobe.com/after-effects/desktop/work-with-transparency-and-compositing/compositing-in-after-effects/compositing-transparency-overview-resources.html
- Adobe alpha 通道、蒙版与 mattes：https://helpx.adobe.com/after-effects/using/alpha-channels-masks-mattes.html

综合：透明、蒙版、mattes、keying、图层合成是独立的技术工序。AI 生成模型输出的是「已经合成好的像素」或「单段视频」，不等于具备可编辑分层、干净 alpha、可用 matte；技术合成是独立的后期工序，需要在生成素材之上单独完成与验收。

## 项目转译

把 AI 生成结果当作素材输入，进入技术合成流程后按以下独立维度验收；保留原生成层与所有修补层的可回查关系。

- **透明度**：是否有显式 alpha 通道；alpha 边缘是否干净（无白边/黑边/半透明噪点）；半透明区域（玻璃/发丝/烟雾）的 alpha 是否与 RGB 解算一致。
- **图层**：生成素材是否已展平；如需分层，是否通过 rotoscope、mask、matte 显式重建；分层命名与归属是否清晰；原生成层与修补层关系可追溯。
- **跟踪**：跟踪点是否附着到正确特征；跟踪曲线在遮挡、变形、光照变化时是否漂移；跟踪数据是否可复用。
- **边缘**：抠像/抠图边缘的发丝、布料、运动模糊处是否漏抠或啃边；边缘过渡是否自然。
- **接触阴影**：人物/道具与地面/桌面接触处的阴影是否补齐；阴影方向、长度、软硬是否与主光源一致；接触点是否闭合。
- **局部修补**：inpaint/局部重生成/补丁图层的边缘是否无缝；修补区域与周围色彩/颗粒/锐度是否一致；修补记录（位置、时间码、来源、版本）是否留痕。

技术合成完成不等于创作剪辑完成，二者分账；保留原生成层与所有修补关系，禁止覆盖原片。

## 可观察验收

- **通过**：六个维度（透明度、图层、跟踪、边缘、接触阴影、局部修补）均独立给出结论；每维有可观察证据（alpha 通道截图、图层结构、跟踪曲线、边缘放大图、接触点对照、修补记录）；原生成层与所有修补层均保留可回查关系；按 B5-08 与创作剪辑分账。
- **失败**：把生成输出当作已具备分层/干净 alpha；只查 RGB 不查 alpha；边缘/接触阴影未单查；修补覆盖原生成层；用「看起来像成片」替代具体维度核验。
- **无法判定**：缺少 alpha 或图层信息；缺少跟踪数据；缺少修补记录；输出被压缩到无法判断边缘/接触细节。

## 不适用条件

- **不能推出**：AI 生成输出已具备可编辑分层或干净 alpha；After Effects 文档中的功能适用于项目实际使用的合成工具；技术合成通过即代表创作剪辑通过；局部修补可无条件替代重生成；任一商业生图/生视频模型默认输出含可用 alpha。
- **结论边界**：本条只规范「生成素材 vs 技术合成」的分账与六维验收，不规定具体合成软件、不替代 B5-08 创作剪辑与技术后期分账的总体协作、不预设具体商业模型输出格式。所有结论以本项目实际文件与图层结构为准。

## 关联

- [[CON-C1-04-分维度素材验收]]：技术合成结果汇入素材验收的技术完整性栏。
- [[CON-B1-06-接触姿态与前后遮挡]]：接触阴影与遮挡边缘的核验对应 B1 接触判断。
- [[CON-B2-03-站位遮挡与纵深]]：图层前后关系与遮挡对应 B2 纵深。
- [[CON-B3-05-颜色管理与创作调色分账]]：技术合成的色彩链路与 B3 颜色管理对齐。
- [[CON-B5-08-创作剪辑与技术后期分账]]：本条是 B5-08 技术后期一侧的具体展开。
- [[REG-知识库规范]]：证据分层、status 与 scope 标注。
