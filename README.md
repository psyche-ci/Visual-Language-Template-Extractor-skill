# Visual Language Template Extractor

一个面向 Codex 的视觉语言提取 Skill：从用户提供的图片或视频参考中识别真实设计画布，提炼可执行的视觉 DNA，确认固定层、可替换层、编辑字段和遮挡关系，再生成可复用的静态或动态模板。

## 核心能力

- 排除截图、录屏和平台界面，只分析真实设计画布
- 提取画布比例、构图、照片插槽、字体、色彩、材质、图层和动效参数
- 使用“模板确认单”确认固定内容、上传区域、可编辑字段和输出规格
- 强制保护人物与目标照片的原始像素，避免整图重绘造成身份漂移
- 生成参考图/复刻图双栏对照的视觉灵感卡片
- 使用白色底板和自适应信息格，完整保留提炼原文与中文 Prompt

## 安装

将本仓库克隆到 Codex 的 skills 目录：

```bash
git clone <repository-url> ~/.codex/skills/visual-language-template-extractor
```

重新启动 Codex 后，可通过 `$visual-language-extractor` 调用。

## 使用流程

1. 上传喜欢的参考图片或视频。
2. 调用 `$visual-language-extractor` 提炼视觉语言。
3. 检查并确认“模板确认单”。
4. 上传目标照片，生成同款复刻图。
5. 确认复刻图后，生成最终视觉灵感卡片。

## 文件结构

```text
visual-language-template-extractor/
├── SKILL.md
├── README.md
└── agents/
    └── openai.yaml
```

## 重要约束

- 不把平台 UI、黑边或录制控件误认为设计元素。
- 不擅自改脸、换人、重绘人物、手部或目标主体。
- 不在用户确认模板结构之前生成最终复刻。
- 不压缩已确认的视觉语言或可复用中文 Prompt。
