# ai-learning

《AI 新人学习规划》W1 的产物：可运行、可推送的 Python 项目骨架。

## 环境

| 组件 | 版本 | 说明 |
|---|---|---|
| Python | 3.12.10 | python.org 官方签名版 |
| uv | 0.13.8 | 依赖与虚拟环境管理 |
| Git | 2.56.0.windows.4 | 版本控制 |

## 依赖

numpy、pandas、matplotlib、jupyter —— 记录在 `pyproject.toml`，锁定在 `uv.lock`。

## 快速开始

```powershell
uv sync                          # 按 uv.lock 还原环境
uv run python -m jupyterlab      # 启动 Jupyter Lab
```

## 验证环境

```powershell
uv run python -c "import numpy, pandas; print(numpy.__version__, pandas.__version__)"
```

## 本机注意事项

**1. numpy 锁定 2.5.4**

本机启用了 Smart App Control（`VerifiedAndReputablePolicyState=1`），会拦截未签名的原生二进制。numpy 2.5.5 的 `_multiarray_umath.pyd` 被拦截导致 `import numpy` 失败，2.5.4 可正常加载，故在 `pyproject.toml` 中固定：

```toml
"numpy==2.5.4",
```

升级前请先在小环境里验证 `import numpy` 是否仍能通过，失败则改回 2.5.4。

**2. 用模块方式启动 Jupyter**

`uv run jupyter lab` 会调用 `.venv\Scripts\jupyter.exe`（uv 生成的无签名启动器），被 SAC 拦截。改用模块入口即可绕过：

```powershell
uv run python -m jupyterlab          # 等价于 jupyter lab
uv run python -m jupyterlab --no-browser
```

**3. 使用国内镜像**

已设置用户环境变量 `UV_DEFAULT_INDEX=https://pypi.tuna.tsinghua.edu.cn/simple`。直连 PyPI 时下载速度约 50 KB/s，改镜像后解析 109 个依赖只需 2.5 秒。

## 进度

- [x] W1-1 六项必装软件就位（uv / Python 3.12 / VS Code / Git / Windows Terminal / 7-Zip）
- [x] W1-2 项目初始化与依赖安装
- [x] W1-3 首次提交
- [x] W1-4 推送至 GitHub
- [x] W1-4 推送至 GitHub
