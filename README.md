# Mac正式版05

小红书对标复刻的 macOS 05版。运行文件与本机已安装、已核验的05快照逐字节一致，保留原有 Skill 标识 `xiaohongshu-reference-replica`。

## 功能

- 内容选择：原意改写、换题重写、从零策划。
- 设计选择：只调位置，或调位置并修改设计细节。
- 统一 Swift 渲染文字、规则图形、路径与图片，输出 PNG 与检查报告。
- 使用已保存的版式继续创作；替换文字和内容图片，保留版式。
- 默认交付有序成品和文字/生图提示词。

## 文件

```text
.codex-plugin/plugin.json
skills/xiaohongshu-reference-replica/
  SKILL.md
  references/复用已有版式.md
  references/统一渲染场景格式.md
  scripts/xhs-fill
  scripts/xhs-render
checksums.sha256
```

## 环境

- macOS；渲染器使用 AppKit/CoreText，不支持 Windows 或 Linux。
- 可运行的 Swift 与 Python 3；Swift 通常通过 Apple Command Line Tools 提供。
- 任务需要参考原图，以及参考链接访问所需的浏览器/登录环境。
- 生图时需要另行安装并配置 `relay-imagegen` Skill 和 `~/.local/bin/relay-imagegen`，或提供合适的现成图片。此包不包含生图中转配置、凭据或依赖插件。
- Canva / Cowart 导入需要对应的可用接口，按 Skill 说明在用户选择后执行。

## 安装运行文件

解压 `Mac正式版05.zip`。将 `skills/xiaohongshu-reference-replica` 整个目录复制到自己的 Codex skills 目录（通常为 `~/.codex/skills/`）。若已存在同名 Skill，先自行备份，避免覆盖正在使用的版本。刷新或重新打开 Codex 后使用该 Skill。

此包附带 `.codex-plugin/plugin.json`，展示名称为“Mac正式版05”；运行文件的 Skill 名称保持原样。

从 Skill 目录运行渲染器：

```bash
scripts/xhs-render /绝对路径/scene.json /绝对路径/新的成品目录
```

已有版式复用：

```bash
python3 scripts/xhs-fill /绝对路径/复用目录 /绝对路径/替换内容.json /绝对路径/新任务/scene.json
scripts/xhs-render /绝对路径/新任务/scene.json /绝对路径/新任务/成品
```

## 版本与完整性

- 发布名称：Mac正式版05。
- 插件包版本：0.5.0（用于标识本次05版打包）。
- 打包日期：2026-10-10。
- 完整运行文件：5个，总计39,836字节。
- `checksums.sha256` 记录全部5个运行文件的 SHA-256；在包根目录运行 `shasum -a 256 -c checksums.sha256` 校验。

本次上传仅包含运行文件、插件描述与安装说明。图片成品、参考素材、测试日志、开发归档和本机配置不在发布包内。
