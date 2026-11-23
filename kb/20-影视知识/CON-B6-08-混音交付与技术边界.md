---
title: 混音、交付与技术边界
created: 2026-11-16
tags: [B6, 声音剪辑, 混音, stems, 声画节奏, 响度, 技术交付]
source: "https://www.taylorfrancis.com/chapters/mono/10.4324/9781315815893-23/cutting-sound-working-multiple-tracks; https://www.taylorfrancis.com/chapters/mono/10.1201/9781003469636-14/final-mix-robin-beauchamp; https://www.taylorfrancis.com/chapters/edit/10.4324/9780080470450-2/evolution-audio-post-production-hilary-wyatt; https://www.bafta.org/awards/film-rules#24.%20SOUND; https://www.itu.int/rec/R-REC-BS.1770/_page.print; https://tech.ebu.ch/files/live/sites/tech/files/shared/r/r128v4_0.pdf; ../../框架V1.1-专业依据与AI创作应用.md"
status: 未验证
type: con
id: CON-B6-08
domain: B6-声音配乐与声画关系/声音剪辑混音与技术交付
evidence-level: E3
scope: 项目内（验收方法未实测）
---

# 混音、交付与技术边界

## 来源命题

《Voice & Vision》把 split edits、sound bridges、ambient layering 列为画面/声音编辑阶段的创作决定。Beauchamp《Final Mix》将 re-recording mixer 的 pre-dub/stem、timing/balance/blend、pan/reverb/delay 与最终 printmaster 联系，说明终混不等于作曲、音乐编辑或声音剪辑。

- 声音剪辑：https://www.taylorfrancis.com/chapters/mono/10.4324/9781315815893-23/cutting-sound-working-multiple-tracks
- 终混：https://www.taylorfrancis.com/chapters/mono/10.1201/9781003469636-14/final-mix-robin-beauchamp

Wyatt/Amyes 区分 tracklaying、mixing、mastering 与按 broadcast/film 规格交付；BAFTA 将 production sound、supervising sound editor、re-recording mixer 分列，是角色边界的行业佐证，不是所有团队的统一岗位模板。

- 后期流程：https://www.taylorfrancis.com/chapters/edit/10.4324/9780080470450-2/evolution-audio-post-production-hilary-wyatt
- BAFTA 官方规则：https://www.bafta.org/awards/film-rules#24.%20SOUND

ITU-R BS.1770-5规定测量主观节目响度和 true-peak 的算法，并提示测量是主观响度的估计、受素材/听者/条件影响；它不是全球统一交付目标。EBU R128（2020）在自身广播体系给出 -23 LUFS 与 -1 dBTP 目标，并允许特殊情况和不同分发系统的限制；不能套用为所有信息流平台标准。

- ITU 官方建议书：https://www.itu.int/rec/R-REC-BS.1770/_page.print
- EBU R128：https://tech.ebu.ch/files/live/sites/tech/files/shared/r/r128v4_0.pdf

## 项目转译

先完成素材与创作编辑，再调整 balance、space、dynamics，最后按渠道检查母版、声道、编码与可替换 stems。B5 的镜头时序与 B6 的声音事件起止、持续、静默、声桥协同，不要求所有画面剪切踩音乐重拍。

为每个版本保留编辑/终混记录、对应画面版本与音频技术信息。先查目标渠道及当期规格再设交付；以完整节目而非单轨判断响度，必要时在手机、耳机等实际听音条件复核。stems 不是终混，导出文件不等于创作完成。

## 可观察验收

- **通过**：对白、音乐、环境的相对可懂度符合任务，声像/空间与动态服务声画目的；stems/master 与画面版本对应，同步、声道、编码及渠道特定响度/峰值经合适算法检查；实际播放无核心失败。
- **失败**：把作曲、音乐编辑、声音设计、终混混为一项；仅靠调大音乐遮对白；声桥掩盖空间/身份错误；为卡拍破坏动作信息；把 -23 LUFS 当所有平台法规或只看总线峰值判合格。
- **无法判定**：缺目标渠道规格、完整节目、测量算法/版本、声道与听音条件；只有素材或导出日志时不能判混音、审美或技术交付通过。

## 不适用条件

- **不能推出**：音乐节奏等于画面节奏；预设或各轨音量一致等于可懂度/情绪/审美一致；标准算法提供所有渠道目标；终混合格自动满足交付；AI 或人工音乐有普遍情绪优劣。
- **结论边界**：本条为项目内未实测的验收方案，不设统一 LUFS、动态范围、声画延迟或模型阈值。EBU 数值只在其适用范围使用，其他平台须查对应规格。

## 关联

- [[CON-B6-01-声音类别与声画系统]]：音轨存在不等于整体声音设计完成。
- [[CON-B6-02-对白旁白与可懂度]]：混音不能以响度代替语言与身份核验。
- [[CON-B6-03-环境声与空间透视]]：空间混音须与输出声道和听音条件共同判断。
- [[CON-B6-04-动作音效与接触证据]]：音效层级不能掩盖接触或动作失败。
- [[CON-B6-05-音乐创作编辑与授权]]：音乐编辑与混音、交付及授权分别留痕。
- [[CON-B6-06-静音留白与声画关系]]：安静段设计与整节目响度不同。
- [[CON-B6-07-声画同步错位与视点]]：同步/错位创作与技术同步检查分别执行。
- [[CON-B5-06-信息揭示与节奏控制]]：混音和声桥须服务信息揭示，不以音量掩盖叙事缺口。
- [[CON-B5-08-创作剪辑与技术后期分账]]：创作剪辑、声音创作与技术导出分别留痕。
- [[CON-B1-07-人物整体的分维度验收]]：核心人物失败不能被混音或响度抵消。
- [[REG-知识库规范]]：标准适用范围、项目转译和实测状态分写。
