# ai-learning

《AI 新人学习规划》W1 的产物：可运行、可推送的 Python 项目骨架。

## 环境

| 组件 | 版本 | 说明 |
|---|---|---|
| Python | 3.12.10 | python.org 官方签名版（本机 Smart App Control 会拦截未签名构建） |
| uv | 0.13.8 | 负责依赖与虚拟环境管理 |
| Git | 2.56.0.windows.4 | 版本控制 |

## 依赖

numpy、pandas、matplotlib、jupyter —— 全部记录在 `pyproject.toml`，锁定在 `uv.lock`。

## 快速开始

```powershell
uv sync                # 按 uv.lock 还原环境
uv run jupyter lab     # 启动 Jupyter（不要用全局 jupyter 命令）
```

## 验证环境

```powershell
uv run python -c "import numpy, pandas, matplotlib; print(numpy.__version__, pandas.__version__)"
uv run jupyter --version
```

## 进度

- [x] W1-1 六项必装软件就位（uv / Python 3.12 / VS Code / Git / Windows Terminal / 7-Zip）
- [x] W1-2 项目初始化与依赖安装
- [x] W1-3 首次提交
- [ ] W1-4 推送至 GitHub
