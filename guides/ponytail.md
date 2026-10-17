# Ponytail 接入与问题对照

执行正文：[003 Ponytail 基础与项目补充编码规范](../standards/003-ponytail-coding.md)。基础使用上游 Ponytail，003 是补充规则，不重写基础提示词。

## 当前接入状态

- 文档依据：2026-10-17 读取上游 main 规则、hook 与相关讨论的快照，非完整代码审计。
- 候选版本：上游已提及 v5.3.0；本项目尚未选择并验证安装版本或提交。接入前必须解析并登记不可变提交，不能将本次阅读 main 视为已固定版本。
- 已完成：补充规范、接入流程、问题对照及本仓库入口。
- 未完成：安装 Ponytail、宿主 hook 信任与配置、新会话加载验证、自动检查、分支合并门禁及模型效果试点。

## 1. 目标项目接入清单

| 字段 | 接入时必须填写 |
| --- | --- |
| 基础版本 | 上游 tag、解析后的完整提交及来源 |
| 宿主 | AI 工具及版本、安装位置、规则与 hook 实际路径 |
| 加载方式 | 插件/skill/宿主规则入口，哪些事件实际受支持 |
| 项目补充 | 003 和 001/002 的本地路径、明确覆盖条款 |
| 状态作用域 | 默认模式、项目/会话是否共享、关闭及恢复方式 |
| 验证 | 已运行命令、结果、加载演练证据、剩余限制 |
| 门禁 | CI 检查名、分支策略及阻断验证结果（如启用） |

先按上游安装文档选择宿主支持的方式，再审阅权限和 hook。不可为安装方便扩大权限或绕过信任。保留上游基础规则的一份加载来源；将本项目补充规范放在宿主明确支持的项目入口，不假定某种注入一定具有更低优先级。

接入后检查实际加载顺序与冲突；若宿主无法可靠应用补充条款，应调整适配而非仅宣称项目规则优先。恢复和上下文压缩的行为取决于宿主版本，必须实测。

## 2. 最小加载摘要示例

将以下内容按宿主支持方式放入目标项目入口，并修正相对路径：

~~~text
基础编码规则使用项目登记的固定版本 Ponytail。
编码任务同时遵循 standards/003-ponytail-coding.md 的明确补充条款。
启动先读取 .ai/memory/index.md、active.md、preferences.md，
再读取 .ai/project-map.md；按任务读取相关历史、模块和真实代码。
简化不得缩减确认需求；验证按风险决定；报告遵循用户语言。
最终编码交付说明实际验证及未验证项；普通讨论不机械追加尾注。
发现规则冲突或加载失败时说明实际状态，不宣称约束已全部生效。
~~~

摘要仅提供入口，不取代完整条款。控制重复注入，历史与模块地图按需读。

## 3. 问题对照（2026-10-17 核查快照）

| 上游记录 | 查到的状态与性质 | 本项目措施 | 仍需核验 |
| --- | --- | --- | --- |
| [#1119](https://github.com/DietrichGebert/ponytail/issues/1119)、[PR #1131](https://github.com/DietrichGebert/ponytail/pull/1131) | 英文报告措辞；维护者认可方向，PR 页面显示 Open | 003 第 4.5 节明确用户语言 | 选定版本的 review/audit 实际输出 |
| [#1098](https://github.com/DietrichGebert/ponytail/issues/1098)、[PR #1129](https://github.com/DietrichGebert/ponytail/pull/1129) | 非编码触发及重复尾注的用户报告；维护者测试不同，暂保留原规则；PR 显示 Open | 第 4.5 节限定过程提示，最终交付仍自足披露 | 目标模型多轮行为，不能为避免重复漏掉首次未验证项 |
| [#1130](https://github.com/DietrichGebert/ponytail/issues/1130) | 模式作用域文档与运行行为矛盾的报告；页面显示 Open，关联 #1135 未取得可核验修复内容 | 第 4.7 节要求声明并实测作用域 | 同仓并行会话、跨仓及宿主差异；不声称已修复代码 |
| [#1036](https://github.com/DietrichGebert/ponytail/issues/1036) | 用户可运行评测提议，维护者同意；页面显示 Open | 第 7 节要求项目及模型试点 | 真实任务质量、成本和长会话占用；旧报告不是当前版本通用结论 |
| [#1085](https://github.com/DietrichGebert/ponytail/issues/1085) | Hermes 安装适配；维护者提供临时接入方法，等待宿主修复 | 记录为适配问题，未使用该宿主则不引入其操作 | 宿主与插件选定版本，不能用 MD 宣称修复 |
| [#1128](https://github.com/DietrichGebert/ponytail/issues/1128) | 界面建议已由维护者在新版实现并关闭 | 无新增修复条款，不将其视为编码缺陷 | 使用相应界面时核验宿主版本 |

这是已阅读记录的对照，不是全部开放 issue 的完整清单，也不是所有报告均已复现。升级或实际安装前重查状态与合并提交，不能依赖 issue 列表缓存或仅凭关闭状态判定目标版本包含修复。

## 4. 三层验收演练

1. 规则：核对基础版本及补充条款路径，无重复全文或互相矛盾副本。
2. 加载：检查配置、实际事件输出及来源；新会话测试中文审查、核心记忆恢复和模式报告。若支持压缩或恢复，再测试重新加载；仅模型自报不算证据。
3. 编码：用小型真实任务验证不遗漏验收、遵守模块风格、覆盖相关失败路径，并同步记忆与地图。
4. 检查：按真实技术栈执行格式、lint、类型和测试；验证失败能在 CI 显示。若配置必需检查，另用可恢复的测试分支验证阻断，遵循项目授权。
5. 并发：两会话在同仓、不同仓的模式与记忆写入分别验证；不把共享状态误当会话隔离。
6. 效果：相同基线、任务、模型及验收下，对比有无 Ponytail 的正确性、总费用、token、工具调用与耗时。新模型或插件升级后按影响复测。

出现加载失败、兼容问题或质量退化时，明确降级为宿主原生项目入口加 MD 规则；若基础 Ponytail 未加载，必须标为降级，不能声称完整接入。保留项目记忆和规范，不靠静默绕过检查完成交付。

## 来源与维护

- [Ponytail 仓库](https://github.com/DietrichGebert/ponytail)
- [基础提示词](https://github.com/DietrichGebert/ponytail/blob/main/skills/ponytail/SKILL.md)
- [安装说明](https://github.com/DietrichGebert/ponytail/blob/main/INSTALL.md)
- [hook 配置](https://github.com/DietrichGebert/ponytail/blob/main/hooks/claude-codex-hooks.json)
- [启动脚本](https://github.com/DietrichGebert/ponytail/blob/main/hooks/ponytail-activate.js)
- [模式与输出适配](https://github.com/DietrichGebert/ponytail/blob/main/hooks/ponytail-runtime.js)

本指南未内置上游代码或完整规则副本。未来分发副本时保留其版权与 MIT 许可；记录采用提交、补丁及升级差异，禁止未经复核自动更新。
