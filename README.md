# tvbox-tools — TVBox「工具」配置

从完整 TVBox 配置里抽出来的**只含工具**的精简配置，配合 `spider.jar` 使用。

## 内容

| 文件 | 说明 |
|---|---|
| `tools.json` | 7 个工具站点的配置，字段结构与原完整配置完全一致 |
| `tools-min.json` | 同上，但去掉 `wallpaper` / `logo`，只保留 `spider` + `sites` —— 给内核较旧或加载异常的客户端兜底用 |
| `spider.jar` | 工具的实现（`csp_ShellInjectTool` / `csp_DecryptConfig` / `csp_ResMgr` / `csp_BinMarket`） |

## 包含的工具

| key | 名称 | api |
|---|---|---|
| `via` | 🌐 Via浏览器[工具] | `csp_ShellInjectTool` (`tool=via`) |
| `DecryptConfig` | 🔓 接口解密[工具] | `csp_DecryptConfig` |
| `ResMgr` | 📦 资源[配置] | `csp_ResMgr` |
| `BinMarket` | 🛠️ 环境[配置] | `csp_BinMarket` |
| `downloader` | ⬇️ 下载器[工具] | `csp_ShellInjectTool` (`tool=dl`) |
| `pushtv` | 📺 PushTV[工具] | `csp_ShellInjectTool` (`tool=filebox`) |
| `shell` | 🐚 默壳管理[工具] | `csp_ShellInjectTool` (`tool=shell`) |

原完整配置里的影视站点、直播源、图库等**全部已剔除**。

## 用法

在 TVBox 里把下面任意一个地址填成「配置地址」：

```
https://500ed59dc8f443dea74b25ed79db1e1e.sg2.agentos-app.run/tools.json
https://500ed59dc8f443dea74b25ed79db1e1e.sg2.agentos-app.run/tools-min.json
https://raw.githubusercontent.com/geuclide97/tvbox-tools/main/tools.json
```

配置里的 `spider` 指向 `.../spider.jar`，md5 为 `e0b6ef0e2dde0871d753d0ac25066d8c`，
与 jar 的实际内容一致 —— 这是配置能被正常加载的前提。

## 备注

* `BinMarket`（环境）依赖外部清单 `https://jk.catvod.site/jk/t4/lab.json`
* `wallpaper` 用 `proxy://do=wallpaper`，由内核自身实现，不需要额外文件
* `logo` 是外部图片地址，可自行替换
