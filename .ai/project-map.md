# 项目地图

## 覆盖信息

- 格式版本：1。人工核验，无生成器。
- 基线：43a0980d2036a6f66c0311a4ce4a4b6836a25067；增量覆盖规范 002、001 风格条款、AGENTS.md、README.md 与三个核心记忆文件；已增量覆盖 003 与 Ponytail 指南；本批次新增 000 并同步入口、目录和记忆。使用前检查后续提交及工作区差异；地图和记忆自身更新不递归刷新基线。
- 范围：下列十二个 Markdown 文件及引用。排除 .git、缓存、构建输出、敏感数据、未来生成索引自身。
- 类型：规范文档仓库，无应用入口、业务代码或运行时依赖。Ponytail、CodeGraph、hook、记忆检索服务、CI 和合并门禁均未启用。
- 未验证：独立新会话恢复、真实软件风格识别、本地 Git 身份采集及团队并发场景。

## 文件结构

~~~text
AGENTS.md                         # AI 入口与读取顺序
README.md                         # 规范目录、接入和能力说明
standards/
  000-agent-orchestration.md       # 主管全局责任与专业子 AI 协作
  001-project-map.md               # 地图、增量上下文、编码风格
  002-persistent-memory.md         # 持久记忆、团队身份及恢复流程
  003-ponytail-coding.md           # Ponytail 基础与项目补充、三层约束
guides/
  codegraph.md                    # 001 的可选工具指南
  ponytail.md                     # 003 的接入验收与问题对照
.ai/
  project-map.md                  # 本地图
  memory/
    index.md                      # 核心记忆入口
    active.md                     # 原因、当前状态、检查点与下一步
    preferences.md                # 共享偏好、来源与范围
~~~

## 已确认关系与修改入口

- [AGENTS.md](../AGENTS.md) 链接核心记忆、地图及两条规范；新会话先恢复核心记忆，再按任务展开。
- [README.md](../README.md) 链接两条规范、AI 入口、地图、三个记忆文件及工具指南。
- [001](../standards/001-project-map.md) 与 [002](../standards/002-persistent-memory.md) 相互关联：风格观察和协作习惯按 002 记录；记忆中的结构事实按 001 核验。
- [CodeGraph 指南](../guides/codegraph.md) 关联 001 和上游，普通任务无需全文读取。
- [记忆索引](memory/index.md) 链接 [当前状态](memory/active.md)、[共享偏好](memory/preferences.md)、002 和本地图；历史按任务读取。
- 新规范放 standards/NNN-topic.md；工具指南放 guides/。同步 README、地图及受影响记忆；通用启动流程改变时更新 AGENTS.md。
- 暂无需模块地图或生成索引；tasks/、decisions/、archive/ 按规模需要创建，保留记忆索引。

## 本仓库风格与核验

共享文档约定由 AGENTS.md 和 memory/preferences.md 维护：中文 Markdown、编号规范、相对链接、简洁标题和表格。无业务代码风格样本；不从文档推断未来代码习惯。

人工核对结构、链接目标、编号、状态、身份来源及引用一致性。无应用测试、格式化器或 lint；不声称自动检查已通过。地图仅导航，修改前读实际文件。浏览器操作身份来自已登录账号，不代表已读取本地 Git 配置。

## 第三条规范接入关系

- [003](../standards/003-ponytail-coding.md) 链接 001/002 及 [Ponytail 指南](../guides/ponytail.md)，以原版固定版本为基础，本地 MD 提供明确补充，不复制基础全文。
- AGENTS.md 为编码任务提供 003 入口，README 列出三条规范和两份指南；记忆保存采纳原因和未部署状态。
- 指南的问题表属于核查快照；安装或升级时重查，不在普通任务中全量读取。当前尚未选择实测通过的上游版本或配置自动门禁。

## 主管与专业角色入口

- [000](../standards/000-agent-orchestration.md) 引用 001/002/003，主管完整读取并核验执行；完成必要熟悉后按任务委派。AGENTS.md 和 README 已将其置于前置入口。
- 子 AI 获取任务契约、适用规范及最小上下文；主管统一协调共享文件、接口、地图和记忆并验收集成结果。
- 当前未接入自动多代理调度；角色专业能力、并发隔离、约束继承及恢复演练均待实际宿主验证。


## 当前规则语义更新

- 000 第 4 节以影响范围、专业跨度、不确定性、风险和依赖关系选择单 AI、专业复核或多专业实施；旧任务 >5/步骤 >10 自动触发规则已废止。复杂度不等于可并行性。
- 003 第 8 节将 Karpathy 四项思想整合为补充约束，链接社区来源，并明确假设、行数、必要联动及验证重试边界。无独立重复 skill 或新文件。
- AGENTS.md 与 README 同步入口，当前记忆记录替代关系；现有文件总数不变。未增加运行工具或自动门禁，仍为人工核验。
