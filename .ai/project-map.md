iven6303-cpu
ai-dev-standards
Repository navigation
Code
Issues
Pull requests
Actions
Projects
Security and quality
More
items
main
Breadcrumbs
ai-dev-standards/.ai
/project-map.md
t
T
Latest commit
iven6303-cpu
Update project-map.md
de76fc0
 · 
History
File metadata and controls
Preview
Code
Blame
44 lines (33 loc) · 2.78 KB
Raw
项目地图
覆盖信息
格式版本：1；人工维护，无生成器。
核验基线：04a7a85007cd8632a0d241517eeb06129be7455a，涵盖此前四条规范和指南订正及历史归档；本批次同时更新 README、入口、记忆与本地图。使用前复核其后相关差异，不因摘要声称“增量覆盖”而跳过实际检查。
范围：下列 14 个 Markdown 文件；排除 .git、缓存、构建输出、敏感数据及未来生成索引自身。
类型：纯规范文档，无业务代码、应用入口、构建和测试配置；无自动调度、插件、hook、CI 或合并门禁。
结构与唯一职责
AGENTS.md                          # 统一启动与角色入口
README.md                          # 规范目录及接入概览
INSTALL.md                         # AI 自动接入与更新协议
standards/
  000-agent-orchestration.md        # 分流、任务契约、主管与子 AI 验收
  001-project-map.md                # 地图有效性、增量阅读、编码风格
  002-persistent-memory.md          # 记忆、身份、状态与归档
  003-ponytail-coding.md            # Ponytail 补充、Karpathy 整合、编码门禁
guides/
  codegraph.md                     # 可选图谱接入
  ponytail.md                      # 基础规则适配与问题核查快照
.ai/
  project-map.md                   # 当前结构导航
  memory/
    index.md                       # 核心及历史入口
    active.md                      # 当前有效状态
    preferences.md                 # 来源明确的共享偏好
    archive/2026-10-17-history.md   # 按需读取、非当前指令

关系与修改入口

AGENTS.md 连接 000、核心记忆与本地图；主管完整理解 001、002、003。各规范中的子流程不覆盖统一启动顺序。

README 列出四条规范及两份指南。CodeGraph 为 001 可选实现；Ponytail 配合 003。普通任务不必加载所有工具指南。

记忆索引 链接 当前状态、共享偏好及归档。旧阈值只保留在历史中。

新增规范或改变语义时同步受影响入口、目录、地图和记忆；无影响则无需强制改文档。已有历史不反复追加到当前状态。

风格与验证

中文 Markdown、相对链接、编号及简洁表格；无业务代码样本。人工核对适用范围、链接及状态，必要时对文件内容作确定性比对。未部署长期校验命令；一次性审查不等于 CI。真实宿主加载、新会话恢复、专业能力与团队并发尚未实测。

 

## 对外接入与更新入口

[INSTALL.md](../INSTALL.md) 由 README 与 AGENTS.md 引用：目标项目本地规范优先，上游副本隔离并登记版本及摘要；地图和记忆由目标项目生成或复用。默认每 7 天由新会话检查，无会话不运行；后台定时需单独配置及验收。此为新增协议文档，不是已实现的安装器、调度或更新程序。本次增量覆盖该文件及 README、入口、当前记忆，使用前按基线复核后续差异。
