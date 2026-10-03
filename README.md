# 项目管理软件在线更新

本仓库保存 Windows 更新清单、旧客户端迁移入口和历史发布备份。业务源码在[项目管理软件源码仓库](https://github.com/codebykyu/project-management)。

## 入口

| 入口 | 用途 |
| --- | --- |
| [阿里云 HTTPS 更新清单](https://8.153.153.189/updates/update/version.json) | 当前客户端检查版本与选择下载包 |
| [update/version.json](update/version.json) | GitHub 中的清单副本及旧客户端迁移信息 |
| [GitHub Pages 迁移入口](https://codebykyu.github.io/project-management-software-updates/update/version.json) | 保留给历史客户端升级迁移 |
| [源码仓库 Releases](https://github.com/codebykyu/project-management/releases) | 新版本安装包与构建备份 |
| [本仓库 Releases](https://github.com/codebykyu/project-management-software-updates/releases) | 历史安装包、模块补丁和模板包 |
| [三层更新发布规则](https://github.com/codebykyu/project-management/blob/windows-online-update/三层更新发布说明.md) | 构建、验证和部署流程 |

## 更新方式

少量功能或页面修改发布小补丁；较大业务或资源修改发布累计文件差量；Python、依赖、稳定启动入口或运行环境变化发布完整安装包。完整包也用于首次安装和修复。同一兼容环境内的累计差量允许用户跳过中间版本。

所有客户端下载地址使用阿里云 HTTPS。先上传并验证安装包、补丁、发行清单和 SHA256，完成更新测试及 Windows 安装验证后，再发布在线版本清单。禁止用旧备份覆盖当前清单。

## 分支与历史

- `main`：当前已提交的更新清单与说明。
- `backup/local-updates-2026-10-03`：本地 v1.3.0 清单快照，仅作备份，不作为当前发布清单。
- `agent/*`：历史更新工作分支，核对合并情况及旧客户端引用后再清理。

历史 Release、补丁、模板包及迁移地址保留供旧客户端使用。版本以在线清单为准；本仓库的 Latest Release 可能是历史基础包，不一定对应当前客户端版本。
