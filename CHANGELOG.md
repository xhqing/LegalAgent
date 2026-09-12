# CHANGELOG

本文件记录本项目（LegalAgent / Justin）每次文件增删改查的变更，写清「为什么改」和「改了什么」。版本号以项目根 `VERSION` 文件为唯一权威（当前 0.1.0）。

## [Unreleased]

### 变更（TODO T8 分流 local 版：个人隐私类待办移出公开仓库）

- **为什么改**：首次 /commit 敏感内容扫描命中——TODO.md T8 属个人隐私类待办，按全局分流规则移入本机 local 文件（分流缘由细节见本机 `CHANGELOG.local.md`）。
- **改了什么**：①新建 `TODO.local.md`（本机隐私版，已入 `.gitignore`）：T8 整条移入，编号保留、时间戳补分流缘由；②`TODO.md`：删 T8、头部补一行分流指引（中性表述）；③`.gitignore`：新增 `TODO.local.md` / `TODO-archive.local.md` / `CHANGELOG.local.md` / `CHANGELOG-archive.local.md` 忽略规则，顺带修正 tmp 注释里已废弃的 `.claude/rules/` 路径引用（改指全局 `~/.claude/CLAUDE.md`）。

### 变更（通用能力句式去 find-skill 提及）

- **为什么改**：全局 find-skill skill 已被用户删除（实际使用中从未用到），各处不再提及；本项目 CLAUDE.md「你的工具」节的通用能力句式仍列着 find-skill，2026-09-12 联动清理。
- **改了什么**：`.claude/CLAUDE.md` 通用能力句式「（anysearch 实时搜索、find-skill 找 skill 等）」→「（anysearch 实时搜索等）」。

### 变更（全局规则路径引用更新：~/.claude/rules/ → ~/.claude/CLAUDE.md）

- **为什么改**：全局通用规则已全部迁入 `~/.claude/CLAUDE.md`，`~/.claude/rules/` 目录已废弃删除，本项目 CLAUDE.md 里两处指向旧目录的引用会指路失效，用户 2026-09-12 指出。
- **改了什么**：`.claude/CLAUDE.md` 两处引用（「工作原则」末条的「见全局 `~/.claude/rules/`」、「你的约束」末条的「通用工作纪律见全局 `~/.claude/rules/`」）均改为指向 `~/.claude/CLAUDE.md`。

### 变更（删除 CLAUDE.md 中「由 Claude Code 自动加载」表述）

- **为什么改**：`.claude/CLAUDE.md` 开头写着「本文件由 Claude Code 在每次会话开头自动加载」，但实际加载它的不止 Claude Code（pi 等其它 agent harness 同样会加载该文件），表述不准确，用户 2026-09-12 要求删除。
- **改了什么**：删除 `.claude/CLAUDE.md` 开头引用块末尾的这句表述，其余内容不变。

### 变更（小组更名同步 + 「你的位置」过时表述修正）

- **为什么改**：用户 2026-09-06 拍板小组更名（任务池投标小组 → 工作接单小组，「任务池投标」降为小组下的接单策略之一），Justin「当前最活跃阵地」表述须同步；顺带发现 `.claude/CLAUDE.md`「你的位置」仍写「团队四个小组中的基础设施小组兼全体成员的法务后盾」——五小组改革（2026-08-23）后已过时（现为五个小组、Justin 隶属财务与法务小组），一并修正。
- **改了什么**：① `.claude/CLAUDE.md`「你的位置」改为「隶属财务与法务小组、跨组服务全团队的合同与收款事项；当前最活跃阵地是工作接单小组的交易保障」；② `README.md` / `README_cn.md` 最活跃阵地 squad 名（task-pool bidding squad → work-intake squad / 任务池投标小组 → 工作接单小组）。

## [0.1.0] - 2026-08-23

### 新增（「固定费用 + 返佣」混合收款结构参考文档）

- **为什么加**：Kit 在分析开源赞助变现仓库 [awesome-oss-sponsorship](https://github.com/Lxcardoza993/awesome-oss-sponsorship)（CC-BY-4.0）时发现，其「固定 + 返佣」混合收费模式（保底现金流 + 转化分成、按月对账、专属口令归因）是「分期付款」之外的另一种收款结构选项，适用于成果可量化归因的服务（引流、转化优化、分销合作），经用户确认提取为参考文档，供合同起草与收款结构设计参考。
- **加了什么**：新建 `references/fixed-plus-revshare.md`——模式定义与一句话合同表述模板、双方风险收益分析、七种交易模式全景表、设计要点、协议条款核对清单，及适用 / 不适用场景边界（原文整理与迁移演绎明确区分标注）。

### 变更（Kit 主项目更名联动：TODO T1 移交指代与路径引用更新）

- **为什么改**：Kit 主项目由 PersonalAssistantAgent 更名为 ExecutiveAssistantAgent（Title「总经理助理」定名后的名字对齐，详见该项目 CHANGELOG）——本项目 TODO T1 的移交方指代与指向该项目 `docs/` 的路径引用随源更名，不改则指路失效。
- **改了什么**：`TODO.md` T1 标题移交方（PersonalAssistantAgent → ExecutiveAssistantAgent）、背景段两处路径（task-pool-bidding-sop.md / service-contract-template.md）、「要做什么」④ 中的副本指代，时间戳随正文改写同步更新至 2026-08-23 23:19。


### 新增（项目立项：法务 Agent LegalAgent）

- **为什么建**：用户确定「电鸭为主渠道接单」路线后，交易保障（合同、收款、纠纷应对）成为持续需求——此前该类工作无归口 agent，散在 Kit 的对话里。新建专职法务 agent 统一负责团队的合同、收款、法务相关内容。
- **建了什么**：完整脚手架——`README.md` / `README_cn.md`（中英双语，含拟人名 Justin 出典：查士丁尼大帝编纂《民法大全》）、`assets/logo.svg`（紫红渐变 ⚖️ 主题）、`VERSION`（0.1.0）、`LICENSE.md`（MIT）、`CHANGELOG.md`、`.gitignore`、`.claude/`（CLAUDE.md 角色定义 + settings 三件套）。`TODO.md` 首批法务待办（T1～T8）从 2026-08-23 Kit 会话中讨论的接单交易保障方案落地转写而来。
