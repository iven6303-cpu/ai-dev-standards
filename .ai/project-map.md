# 项目地图

## 覆盖信息

- 格式版本：1。人工核验，无生成器。
- 基线：43a0980d2036a6f66c0311a4ce4a4b6836a25067；增量覆盖规范 002、001 风格条款、AGENTS.md、README.md 与三个核心记忆文件。使用前检查后续提交及工作区差异；地图和记忆自身更新不递归刷新基线。
- 范围：下列九个 Markdown 文件及引用。排除 .git、缓存、构建输出、敏感数据、未来生成索引自身。
- 类型：规范文档仓库，无应用入口、业务代码或运行时依赖。CodeGraph、记忆检索服务和 CI 均未启用。
- 未验证：独立新会话恢复、真实软件风格识别、本地 Git 身份采集及团队并发场景。

## 文件结构

~~~text
AGENTS.md                         # AI 入口与读取顺序
README.md                         # 规范目录、接入和能力说明
standards/
  001-project-map.md               # 地图、增量上下文、编码风格
  002-persistent-memory.md         # 持久记忆、团队身份及恢复流程
guides/
  codegraph.md                    # 001 的可选工具指南
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
