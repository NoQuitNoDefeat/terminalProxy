# 🚀 终端代理设置指南 (Quick Start)

以下命令用于在当前终端会话中**临时设置**代理。
> ⚠️ **注意**：请将示例中的端口 `10808` 修改为您实际使用的代理软件端口（常见端口如 7890, 10809 等）。

## 1. Windows PowerShell
适用于 Windows 10/11 默认终端或 VS Code 终端。

```powershell
# ✅ 开启代理 (设置环境变量，小写 + 大写，兼容更多程序)
$env:http_proxy="http://127.0.0.1:10808"
$env:https_proxy="http://127.0.0.1:10808"
$env:HTTP_PROXY=$env:http_proxy
$env:HTTPS_PROXY=$env:https_proxy

# ✅ 验证是否生效 (如有输出则表示成功)
$env:http_proxy
$env:HTTP_PROXY

# ⛔ 关闭代理 (清空环境变量)
$env:http_proxy=$null
$env:https_proxy=$null
$env:HTTP_PROXY=$null
$env:HTTPS_PROXY=$null
or
# ⛔ 关闭代理 (清空环境变量)
$env:http_proxy=""
$env:https_proxy=""
```
```powershell
# 替换为您自己的代理地址和端口
$ProxyAddress = "http://127.0.0.1:10809" 

# 设置 HTTP 代理
$env:http_proxy = $ProxyAddress

# 设置 HTTPS 代理（Git 连接 GitHub 主要使用 HTTPS）
$env:https_proxy = $ProxyAddress

# 确认设置是否成功（可选）
$env:https_proxy
```
## 2. Windows CMD

适用于旧版命令提示符 (`cmd.exe`)。

```cmd
:: ✅ 开启代理
set http_proxy=http://127.0.0.1:10808
set https_proxy=http://127.0.0.1:10808

:: ✅ 验证是否生效
echo %http_proxy%

:: ⛔ 关闭代理
set http_proxy=
set https_proxy=
```

## 3. macOS / Linux (Bash & Zsh)

适用于 Mac 终端、Linux 服务器或 Windows WSL。

```bash
# ✅ 开启代理（同时设置小写/大写，兼容更多工具）
export http_proxy="http://127.0.0.1:10808"
export https_proxy="http://127.0.0.1:10808"
export HTTP_PROXY="$http_proxy"
export HTTPS_PROXY="$https_proxy"

# ✅ 验证是否生效
echo "$http_proxy"
echo "$HTTP_PROXY"

# ⛔ 关闭代理
unset http_proxy https_proxy HTTP_PROXY HTTPS_PROXY
```

## 4. Git 专属配置

如果您只需要加速 Git 操作（如 `git clone`），可以使用以下命令进行**永久配置**。

```bash
# ✅ 设置全局代理 (所有仓库生效)
git config --global http.proxy http://127.0.0.1:10808
git config --global https.proxy http://127.0.0.1:10808

# 如使用 SOCKS5 代理，可使用：
# git config --global http.proxy socks5://127.0.0.1:10808
# git config --global https.proxy socks5://127.0.0.1:10808

# ⛔ 取消全局代理
git config --global --unset http.proxy
git config --global --unset https.proxy
```


