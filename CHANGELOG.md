# Changelog / 变更日志

All notable changes to this project will be documented in this file.

本项目的所有重要变更都会记录在这里。

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project follows semantic change grouping.

格式基于 [Keep a Changelog](https://keepachangelog.com/en/1.1.0/)，并按语义变更类型归类。

## [Unreleased]

### Added / 新增

- Added `ip-illustrations` as a multi-IP workflow library with one routing entrypoint and isolated per-IP workflows.
- 新增 `ip-illustrations` 多 IP 工作流库，包含统一路由入口和互相隔离的单 IP 工作流。
- Added three built-in IP workflows: `pageworker`, `threadsmith`, and `holeseeker`.
- 新增 3 个内置 IP 工作流：`pageworker`、`threadsmith`、`holeseeker`。
- Added a custom IP workflow spec for generating future Markdown workflow packages.
- 新增 IP 定制工作流规格，用于后续生成新的 Markdown 工作流包。

### Changed / 变更

- Replaced the single-IP `pageworker-illustrations` package with `ip-illustrations`.
- 将单 IP 的 `pageworker-illustrations` 包替换为 `ip-illustrations`。
- Reworked the main skill from direct image-prompt rules into an IP router and workflow dispatcher.
- 将主 Skill 从直接生图规则改为 IP 路由和工作流调度器。
- Updated README, examples, notice, agent metadata, and references around the multi-IP workflow model.
- 围绕多 IP 工作流模型更新 README、示例、声明、agent 元数据和 references。

### Removed / 移除

- Removed the previous single-IP active workflow structure from the installable skill package.
- 从主动可安装 Skill 包中移除旧的单 IP 工作流结构。

### Fixed / 修复

- Kept legacy upstream images and author assets isolated under `legacy-assets/` so they do not affect active IP routing or generation.
- 将历史上游图片和作者资产隔离在 `legacy-assets/`，避免影响当前 IP 路由和生成。
