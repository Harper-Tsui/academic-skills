# academic-skills

用于学术研究与写作的 agent skills 合集。三个子目录是三个独立上游项目的快照，各自保留原作者的 `LICENSE`、README 与引用信息。

| 目录 | 上游仓库 | 用途 | 许可证 |
| --- | --- | --- | --- |
| `literature-review-skills/` | [xingtaxueshu/literature-review-skills](https://github.com/xingtaxueshu/literature-review-skills) | 文献综述：问题提炼 → 模块拆分 → 方法比较 → 矛盾梳理 → 研究空白 | MIT |
| `academic-writing-skills/` | [WenyuChiou/academic-writing-skills](https://github.com/WenyuChiou/academic-writing-skills) | 论文写作与审稿：框架、分段写作、四遍全稿审阅、审稿意见回应 | MIT |
| `humanities-writing-companion/` | [tizzy916/humanities-writing-companion](https://github.com/tizzy916/humanities-writing-companion) | 人文学科写作：四层批判、魔鬼代言人、声音保护、盲读、AI 使用披露 | CC BY-NC 4.0（仅限非商业用途） |

## 快照时点

| 上游 | 提交 | 日期 |
| --- | --- | --- |
| literature-review-skills | `177bec5` | 2026-10-28 |
| academic-writing-skills | `404eb2a` | 2026-10-29 |
| humanities-writing-companion | `e097ff6` | 2026-09-22 |

同步说明：本仓库是快照，不会自动跟随上游更新。要拉取最新版本，重新执行下方命令覆盖对应目录即可。

```bash
git clone --depth 1 https://github.com/<上游>.git /tmp/upstream
rsync -a --exclude .git /tmp/upstream/ ./<目录名>/
```

整理时只做了一处删减：`academic-writing-skills/skills/*/assets/examples/` 下的示例图片（三份重复，每份约 4.6 MB）未收录，其余文件与上游一致。该仓库的 `skills/` 仍有完整 SKILL.md 与 references，不影响使用。

## 如何安装到本地

这里存放的是源码，不是已安装状态。实际使用时，把需要的 skill 文件夹复制到 agent 的技能目录：

```bash
# Claude Code：用户级（对所有项目生效）
cp -r literature-review-skills ~/.claude/skills/

# 或项目级（只在当前项目生效）
cp -r humanities-writing-companion ./.claude/skills/
```

`academic-writing-skills` 推荐通过插件市场安装以保持可更新：

```bash
claude plugin marketplace add WenyuChiou/ai-research-skills
claude plugin install academic-writing-skills@ai-research-skills --scope user
```

Claude 桌面版可在设置 → 能力/技能中上传打包成 `.zip` 的 skill 文件夹（目录内须含 `SKILL.md`）。

## 许可与署名

各子目录的使用条款以各自的 `LICENSE` 为准。

- `literature-review-skills`、`academic-writing-skills`：MIT，可自由使用与再分发，保留版权声明即可。
- `humanities-writing-companion`：CC BY-NC 4.0，学术研究、教学、个人项目可用，需署名；商业用途需联系原作者 `shencong916@gmail.com` 取得授权。作者 Shen Cong，建议引用：`10.5281/zenodo.20280772`。

如果在论文中使用，请按各上游 README 中的方式注明出处。
