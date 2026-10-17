# ai-dev-standards

用于软件项目的 AI 开发规范与约束，按主题逐步扩展，每条规范保留唯一正文。

## 规范目录

| 编号 | 规范 | 状态 |
| --- | --- | --- |
| 000 | [主管统筹与专业子 AI 协作](standards/000-agent-orchestration.md) | 已采纳；调度接入待验证 |
| 001 | [项目地图与增量上下文](standards/001-project-map.md) | 已采纳 |
| 002 | [持久记忆与会话恢复](standards/002-persistent-memory.md) | 已采纳 |
| 003 | [Ponytail 基础与项目补充编码规范](standards/003-ponytail-coding.md) | 已采纳；插件接入待验证 |

000：主管完整理解并严格执行 001/002/003，先恢复记忆、熟悉项目及需求，再拆解任务、组建专业角色并调度协作；主管核验结果、集成并承担最终责任。子 AI 专业度通过任务匹配、方法和证据评估。

001：通过地图按需读取真实代码、同步结构并识别模块风格。

002：保存需求、原因、进度及适用习惯，核验 Git 身份来源与团队归属。

003：固定版本 Ponytail 为基础，项目 MD 补充完整性、复用、风险验证、兼容性、语言及技术债约束。

## AI 阅读入口

从 [AGENTS.md](AGENTS.md) 开始，按 000 明确主管责任；读取[记忆索引](.ai/memory/index.md)、[当前状态](.ai/memory/active.md)、[共享偏好](.ai/memory/preferences.md)及[项目地图](.ai/project-map.md)，核验当前事实。主管完整读取 001/002/003；子 AI 读取自身任务适用条款和必要上下文，不重复全仓扫描。

## 三层接入方式

1. 规则与记忆：将适用规范保存到目标仓库并保留来源、版本；建立地图和记忆，登记 Ponytail 固定版本及补充条款。
2. 加载与调度：按宿主实际支持的规则入口、skill、hook 和子代理接口接入；验证启动、恢复、角色约束继承、模式与文件隔离，避免重复注入。
3. 自动验证：接入格式、lint、类型、测试及主管证据核验；需要时配置 CI 必需检查、分支保护及审查权限并验证阻断效果。

MD 不会自行创建真实子 AI，也不保证规则已加载或执行；宿主不支持时明确降级。项目规则不覆盖更高优先级指令或权限，记忆中的提交合并习惯不替代当次授权。

## 指南与参考

- [Ponytail 接入与问题对照](guides/ponytail.md)
- [CodeGraph 可选接入](guides/codegraph.md)
- 000 参考 [Agency Agents](https://github.com/msitarzewski/agency-agents)、[BMAD-METHOD](https://github.com/bmad-code-org/BMAD-METHOD)、[AOrchestra](https://github.com/FoundationAgents/AOrchestra)，未将这些项目安装为运行依赖。

## 扩展方式与实际状态

新规范放 standards/NNN-topic.md；指南放 guides/。同步目录、地图、入口及受影响记忆，保留既有编号。

当前是纯 Markdown 仓库，已建立 000–003 四条规范、两份指南、地图和核心记忆，采用人工结构、链接与状态核验。尚未部署自动多代理调度、Ponytail、CodeGraph、hook 加载、CI 或合并门禁；真实软件任务、新会话和团队协作演练待验证。
