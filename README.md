# 🚀 终端代理设置指南 (Quick Start)

以下命令用于在当前终端会话中**临时设置**代理。
> ⚠️ **注意**：请将示例中的端口 `10808` 修改为您实际使用的代理软件端口（常见端口如 7890, 10809 等）。

## 1. Windows PowerShell
适用于 Windows 10/11 默认终端或 VS Code 终端。

```powershell
# 开启代理 (设置环境变量)
$env:http_proxy="[http://127.0.0.1:10808](http://127.0.0.1:10808)"
$env:https_proxy="[http://127.0.0.1:10808](http://127.0.0.1:10808)"

# 验证是否生效 (如有输出则表示成功)
$env:http_proxy

# 关闭代理 (清空环境变量)
$env:http_proxy=""
$env:https_proxy=""
```
## 2. Windows CMD

适用于旧版命令提示符 (`cmd.exe`)。

```cmd
:: 开启代理
set http_proxy=[http://127.0.0.1:10808](http://127.0.0.1:10808)
set https_proxy=[http://127.0.0.1:10808](http://127.0.0.1:10808)

:: 验证是否生效
echo %http_proxy%

:: 关闭代理
set http_proxy=
set https_proxy=
```

### 3\. macOS / Linux (Bash & Zsh)

适用于 Mac 终端、Linux 服务器或 Windows WSL。

```bash
# 开启代理
export http_proxy="[http://127.0.0.1:10808](http://127.0.0.1:10808)"
export https_proxy="[http://127.0.0.1:10808](http://127.0.0.1:10808)"

# 验证是否生效
echo $http_proxy

# 关闭代理
unset http_proxy https_proxy
```

### 4\. Git 专属配置

如果您只需要加速 Git 操作（如 `git clone`），可以使用以下命令进行**永久配置**。

```bash
# 设置全局代理 (所有仓库生效)
git config --global http.proxy [http://127.0.0.1:10808](http://127.0.0.1:10808)
git config --global https.proxy [http://127.0.0.1:10808](http://127.0.0.1:10808)

# 取消全局代理
git config --global --unset http.proxy
git config --global --unset https.proxy
```

```

***

### 💡 建议
在您粘贴之后，可以使用 GitHub 的 **"Preview" (预览)** 按钮查看效果。这段 Markdown 代码使用了层级标题和代码块高亮，在 GitHub 页面上显示会非常漂亮且易读。

**下一步：**
如果您希望让这个项目更完善，您是否需要我为您写一段关于 **"如何将这些命令封装成一个快捷脚本（Alias）"** 的说明？这样用户只需要输入一个单词（比如 `proxy_on`）就能开启代理。
```
