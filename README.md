# Oh-My-ClaudeCode

> 一个从 0 到 1 手写的、类 Claude Code 的 Agent Harness，单文件实现，开源分享。
> 代码里可能还有不少错误和不够严谨的地方，欢迎大家批评指正、一起完善。

## 关于本项目

我用一个 `agent-loop.py` 手搓了一套 Claude Code 的核心源码，覆盖了从 Agent 内核、上下文管理、记忆，到工具控制、权限、子代理、技能加载、后台任务、Cron 调度等几乎完整的能力链路。

## 已实现能力

- Agent 内核 / 主循环
- 工具控制与工具注册表：`bash` / `read_file` / `write_file` / `edit_file` / `glob` / `todo_write` / `load_skill` / `task`（子代理）
- 权限控制与 Hooks：`PreToolUse` / `PostToolUse` / `UserPromptSubmit` / `Stop`，危险命令拦截
- 记忆系统：`user` / `feedback` / `project` / `reference` 四类记忆，含索引、检索与固化
- 任务系统：`Task` / `TaskStore`，支持创建、认领、完成与依赖检查
- 上下文压缩：`ContextCompactor` + 自动压缩
- 后台任务与 Cron 定时调度
- 技能加载 `SkillLoader`
- 子代理 `Subagent`

## 快速开始

1. 安装依赖：`pip install -r requirements.txt`
2. 配置环境变量：复制 `.env.example` 为 `.env`，填入 `ANTHROPIC_API_KEY` 和 `MODEL_ID`
3. 运行：`python agent-loop.py`

## 致谢

特别感谢 langchain code 项目，本项目参考并基于它的实现思路手搓而成。

## 联系我

- 邮箱：`3211840032@qq.com`

欢迎提 Issue / PR，也欢迎直接邮件交流。