# 项目约定 · 焰行者

## 交付形态
- 游戏/网页类交付物一律做成**单个 HTML 文件**（样式与脚本内嵌），用户明确要求"不要分开的"。
- 不使用任何外部依赖、CDN、图片或音频资源，保证离线双开即玩。

## 技术约定
- 原生 Canvas 2D + requestAnimationFrame，固定 60Hz 逻辑步长（`STEP = 1000/60`）。
- 游戏内容全部数据驱动：`CHARACTERS` / `ENEMY_TYPES` / `LEVELS` / `DIALOGUES` 四个数组，改数据即改游戏。
- 状态机单一入口变量 `state`：title / dialog / playing / paused / cleared / result / dying。

## 开发环境
- 用户在 VS Code 中编辑，已配置 `.vscode/`（UTF-8、Live Server 5500、Chrome 调试）。
- 文件必须保持 UTF-8 无 BOM，换行 LF。
- 调试入口：URL hash `#play=1`~`#play=4`（加 `run` 自动向右跑）、`#screen=chars|levels|dialog|result`。
