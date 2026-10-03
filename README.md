# ecom-prompt-skills

电商 AI 生图提示词技能合集（ZCode / Claude Code 兼容）。仓库内每个子目录即一个独立技能，可直接拷入本地技能目录使用。

> **版权与传播声明**：本仓库内容归仓库所有者所有，为私有存档用途。在版权归属确认并发布公开许可之前，请勿克隆、转载或公开传播本仓库内容。

## 技能清单

| 技能 | 内容 | 规模 |
|---|---|---|
| `ecom-prompt-sop` | 电商生图提示词 SOP 全库：34 篇按品类与场景分类的中文提示词模板，含全平台主图/详情页（含跨境）、白底图、买家秀、爆款反推与风格拆解、品类专项（服饰/3C/美妆/美食/家具/包包/海产/杯壶/檀木）、SKU 批量与图内文字翻译、模特换装与电商视频生成/视频反推 | 1 SKILL.md + 34 篇 |
| `ecom-main-image-prompts` | 全平台电商主图生图提示词导演：基于产品图动态规划整套主图方案，内置产品锁定、平台合规、模特人脸、图内文字、信息真实性硬规则 | 1 SKILL.md + 平台规则 |
| `ecom-detail-page-prompts` | 全平台电商详情页生图提示词导演：按品类与决策链路规划详情页页面结构与逐页提示词（默认淘宝，其他平台可在输入中指定） | 1 SKILL.md |

## 安装

把想要的技能目录整体拷入本地技能目录即可，路径形如 `<技能目录>/<技能名>/SKILL.md`：

- ZCode：`~/.agents/skills/<技能名>/`（或项目级 `<项目>/.agents/skills/<技能名>/`）
- Claude Code：`~/.claude/skills/<技能名>/`

以 `ecom-prompt-sop` 为例：

```bash
git clone https://github.com/A2194008525/ecom-prompt-skills.git
cp -r ecom-prompt-skills/ecom-prompt-sop ~/.agents/skills/
```

新开会话后技能自动被发现；触发方式为自然语言命中（如「给这件卫衣出详情页提示词」「把这批 3:4 主图转 1:1」）。

## 与本地技能目录的同步

本地在用副本位于 `C:\Users\ADC\.agents\skills\`，本仓库是其存档镜像。技能更新后，把对应技能目录重新拷入本仓库并提交推送：

```bash
cp -r ~/.agents/skills/ecom-prompt-sop .
git add ecom-prompt-sop && git commit -m "feat(ecom-prompt-sop): 更新说明" && git push
```

仓库根目录与本地技能目录为单向同步（本地 → 仓库），不要在仓库内直接改技能再拷回。
