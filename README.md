# tvbox-tools — TVBox「工具」配置

从完整的 TVBox 配置里抽出来的一份**只含工具**的精简配置，配合 `spider.jar` 使用。

## 内容

```
tools.json   只含 7 个工具站点的 TVBox 配置
spider.jar   工具的实现（csp_ShellInjectTool / csp_DecryptConfig / csp_ResMgr / csp_BinMarket）
```

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

原先完整配置里的影视站点、直播源、图库等**全部已剔除**。

## 用法

把 `tools.json` 放进任意可 HTTP 访问的位置，然后在 TVBox 里作为配置地址加载。

`spider.jar` 的 md5 为 `e0b6ef0e2dde0871d753d0ac25066d8c`，
与 `tools.json` 里 `spider` 字段声明的 md5 一致 —— 这是配置能正常加载的前提。

### 想让 jar 也走本仓库

把 `tools.json` 里的 `spider` 换成：

```
https://raw.githubusercontent.com/<你的用户名>/<仓库名>/main/spider.jar;md5;e0b6ef0e2dde0871d753d0ac25066d8c
```

## 备注

* `BinMarket`（环境）依赖外部清单 `https://jk.catvod.site/jk/t4/lab.json`
* `wallpaper` 用 `proxy://do=wallpaper`，由 jar 内部实现，不需要额外文件
* `logo` 是外部图片地址，可自行替换
