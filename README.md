# premise-and-config-audit · 前提与配置合规审计

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE.md)
[![Agent Skill](https://img.shields.io/badge/Agent%20Skill-SKILL.md-blue.svg)](SKILL.md)
[![Premortem](https://img.shields.io/badge/premortem-assumption%20testing-brightgreen.svg)](SKILL.md)
[![Config Audit](https://img.shields.io/badge/config-drift-Well--Architected-2ea44f.svg)](SKILL.md)
[![Diagnosis Only](https://img.shields.io/badge/diagnosis--only-no%20auto--changes-informational.svg)](SKILL.md)
[![Version](https://img.shields.io/badge/version-1.0-informational.svg)](SKILL.md)

SynomosAI 四支柱体系：**身份（Identity）· 溯源（Traceability）· 治理（Governance）· 共生（Symbiosis）**——当 AI 进入商业，可信是唯一的硬通货。

> 本仓库属于 [SynomosAI](https://github.com/SynomosAI) 生态技能包的一员。生态全景见 [`synomosai-skills`](https://github.com/SynomosAI/synomosai-skills)，理论站位见 [`traceability-audit`](https://github.com/SynomosAI/traceability-audit)。

**关键词 / Keywords**：前提验证 · 假设检验 · premortem · 配置审计 · 配置漂移 · 工具链盘点 · AWS Well-Architected · SRE config · compliance audit

「前提验证 + 配置审计」方法论技能：开工前先证伪最危险假设（不把预判当事实），审工具 / 配置时先盘真实状态再对标标准。是既有铁律「先查标准再主张（输出侧）」的互补补丁——「对内假设先验证（问题侧）」。**只诊断、不改配置**，敏感项列 P0 待用户确认。

---

## ✨ 特性 / Features

- **前提验证 5 步**：假设枚举 → 可证伪性排序（重要性 × 证据）→ 最小成本实测 → 影响评估（错了是否崩塌）→ 再架构。
- **配置审计三棱镜**：盘点真实状态（实测不凭记忆）→ 对标标准（AWS Well-Architected / SRE / Delinea 身份治理）→ 诊断（好 / 缺口 / 冗余）→ 分级建议 P0/P1/P2。
- **理论背书**：Premortem（Gary Klein, HBR 2007）、Assumption Testing（CB Insights：42% 创业失败因未验证需求假设）、AWS Well-Architected、Google SRE 配置管理、第一性原理 / 逆向思维 / 安全边际。
- **工具可见性纪律**：审计隐藏目录（`.` 开头）时不依赖默认 Grep/Glob，避免「没找到」的假阴性。
- **安全边界**：删技能 / 连连接器 / 改自动化等敏感动作必须单独待用户确认。

---

## 🚀 快速开始 / Quick Start

> 前置：本技能为方法论 / 清单型，无可执行依赖；启动新方案或复盘工具链时调用。

```bash
# 1. 克隆本仓
git clone https://github.com/SynomosAI/premise-and-config-audit.git
cd premise-and-config-audit

# 2. 查看技能主文件（前提验证 5 步 / 配置审计三棱镜 / 检查清单）
cat SKILL.md
```

要启动一个方案前，先按模块一列出 Top 3 假设并标注「事实 or 预判」；要复盘工具链时，按模块二实测连接器 / 技能 / 自动化的真实状态再对标。

```text
触发词示例：
  前提 / 假设 / 验证 / 审计 / 配置漂移
  工具链 / 冗余 / 激活不足 / 复盘为什么方案走偏
```

---

## 📖 使用方式 / Usage

1. 克隆本仓库或将技能目录放入 Agent 技能目录；
2. 重大决策 / 架构启动前走「模块一：前提验证法则」；
3. 定期走「模块二：配置审计三棱镜」，输出 Markdown 审计文档（现状 / 对标 / 诊断 / 分级建议）；
4. **只诊断，不改配置**——敏感项列 P0 待用户确认。

### 审计文档示例（节选）

```text
【配置审计 · 2026-08-23 快照】
  连接器：声称已连 20 个 → 实测真实连通 4 个（其余为建完即睡）
  技能：已装 77 个 → 近 30 天激活 15 个
  诊断：规划过剩、激活不足；存在 3 组功能域重叠
  分级建议：
    P0：停用 3 个冗余技能（待用户确认后执行）
    P1：补连 2 个高价值连接器（待用户确认）
    P2：建立季度配置复审节奏
```

---

## 🧩 仓库结构 / Repository layout

```text
premise-and-config-audit/
├── README.md                # 本文件
├── README.en.md             # 英文版说明
├── SKILL.md                 # 技能主文件（前提验证 / 配置审计 / 踩坑固化）
├── LICENSE.md               # MIT License
├── llms.txt / llms-full.txt # 给 AI 的索引与完整文本
├── AGENTS.md                # 给 AI Agent 的工作指引
├── SECURITY.md              # 安全策略
└── CODEOWNERS               # 代码所有者
```

---

## 🔎 方法论 / Methodology

- **Premortem**（Gary Klein, HBR 2007）：假设项目已失败 → 反向找因，比普通头脑风暴多发现约 30% 失败因。
- **Assumption Mapping**：假设显性化，按「重要性 × 证据」排序，高重要 + 低证据者立即用最便宜实验证伪。
- **AWS Well-Architected**：按真实配置答，不按纸面设计；配置漂移当运营告警；周期性复审。
- **Google SRE**：控制台改会漂移，IaC 才持久；配置即代码。
- 引用任何理论前先用 WebSearch 速查确凿出处；查不到就明说「没查到」，不编造年份 / 机构。

---

## ❓ 常见问题 / FAQ

- **审计会自动改我的配置吗？** 不会。只产出诊断文档；删技能 / 连连接器 / 改自动化等敏感动作必须你确认后才执行。
- **凭记忆答不行吗？** 不行。配置审计的核心是实测真实状态，凭记忆会漏（曾出现「77 连 4、16 自动化 15 睡」的误判）。
- **结论是法律意见吗？** 不是。本技能为方法论与清单；正式合规决策请独立核实。

---

## License / 许可

本项目以 **MIT** 许可发布，详见仓库根目录 [LICENSE.md](LICENSE.md)。版权：© 2026 注册老炮@MedXpert。

---

## 🔒 安全 / Security

如发现安全问题，请按 [`SECURITY.md`](SECURITY.md) 的方式私下报告，不要在公开 issue 中披露。

## 🤝 贡献 / Contributing

欢迎补充检查清单与踩坑案例；修改 `SKILL.md` 时保持 YAML frontmatter 字段兼容。代码所有者见 [CODEOWNERS](CODEOWNERS)。

---

## 免责声明

本仓库内容为 SynomosAI 的**理论站位与工具化探索**，不代表任何已获认证、已商业化交付或已服务特定客户的声明；文中涉及的 AWS Well-Architected、Google SRE、Premortem 等外部方法与文献信息为公开资料转述，正式引用前请**独立核实**。API、授权码与形象大使等为路线图（roadmap）事项，尚未上线。
