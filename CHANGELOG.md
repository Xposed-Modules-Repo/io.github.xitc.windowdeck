# 更新记录

## 0.4.8-beta.28 · 包名迁移

- 包名、源码命名空间、Xposed 入口、Provider authority 和内部通信统一迁移为 `io.github.xitc.windowdeck`。
- 符合 LSPosed 模块仓库的 GitHub 用户命名规则，无需独立域名。
- 新版独立安装，不能覆盖 `dev.windowdeck.app`；需重新配置 Root 与 LSPosed。
- Actions 发布标签采用 `versionCode-versionName`，校验 APK 包名、版本及原发布签名；保留每日有变更才发布和草稿上传流程。
- 基于公开 beta.27，不包含本地 dev.128 开发改动。

验证：17 项发布流程测试、12 组布局回归、APK 构建和发布证书检查通过。未进行新包名版本的真机安装或行为验收。

[下载本版](https://github.com/Xposed-Modules-Repo/io.github.xitc.windowdeck/releases/tag/83-0.4.8-beta.28) · [完整历史更新](https://github.com/xitc/windowdeck/blob/main/CHANGELOG.md)
