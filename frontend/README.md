# Paper Orchestra 前端

本目录包含 Paper Orchestra 的 Streamlit 前端。

## 如何在本地启动演示

1. 确保已激活环境并安装依赖。
2. 进入项目根目录：
   ```bash
   cd paper-orchestra
   conda activate paper_orchestra
   ```
3. 运行 Streamlit 应用：
   ```bash
   streamlit run frontend/app.py
   ```
4. 在浏览器中打开终端提供的 URL（通常为 `http://localhost:8501` 或类似地址）。

## 如何终止未完成的写作进程

前端会启动一个后台进程（`paper_writing_cli.py`）来处理论文生成。

### 自动清理
在 Linux 上，应用已配置为在 Streamlit 服务器进程停止时自动终止后台进程。在运行 `streamlit run` 的终端中按 **Ctrl+C** 即可清理正在运行的流水线。

### 手动清理
如果从前端断开连接，或服务器意外停止而未清理，后台可能残留孤儿进程。可手动终止：

```bash
pkill -f paper_writing_cli.py
```

或先查找进程 ID（PID）：
```bash
pgrep -f paper_writing_cli.py
```
然后终止：
```bash
kill <PID>
```