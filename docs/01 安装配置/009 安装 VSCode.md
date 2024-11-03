# 009 安装 VSCode

如果已经安装过 VSCode，想要重新安装的话，可以卸载 VSCode [^uninstall]：

- 卸载 VSCode

- 删除 `%APPDATA%\Code` ，一般是 `C:\Users\[username]\AppData\Roaming\Code`

- 删除 `%USERPROFILE%\.vscode`，一般是 `C:\Users\[username]\.vscode`

打开 https://code.visualstudio.com/Download [^vscode] ，选择 System Installer x64 下载 VSCode，安装。

## 配置

- 禁用 Trust: security.workspace.trust.enabled
- oneDarkPro.markdownStyle
- fontfamily: `'Fira Code', Consolas, dengxian, 'Courier New', monospace`
- fontsize: 20

## 添加插件

- One Dark Pro
- Fluent Icons
- vscode-icons
- Markdown All in One
- Markdown Footnotes
- Markdown Preview Mermaid Support
- Remote - SSH

---

- Backup and Sync Settings 登录账号同步配置

## References

[^uninstall]:https://code.visualstudio.com/docs/setup/uninstall
[^vscode]: https://code.visualstudio.com
