# xxx的开发说明

请在这个 Minecraft 模组项目中实现一个“xxx”模组。先阅读仓库中的 `AGENTS.md`，并以项目实际的 `gradle.properties`、`settings.gradle`、各模块构建文件、现有源代码和资源为准。不要凭记忆猜测 Minecraft API，也不要升级项目版本。
这是通过Architecture online generator生成的适用于xxx版本的fabric和Neoforge的模组模版.

## 功能目标

xxx


## 实现规则

先确认本项目启用的平台和现有架构。共享逻辑放在 `common`，Fabric 专属代码放在 `fabric`，NeoForge 专属代码放在 `neoforge`。不要在 `common` 中导入 Fabric 或 NeoForge 专属 API，也不要混用两个平台的 API。

其他xxx

## 资源清单
Xxx


所有资源都要放在正确的平台共享资源目录中，不能只写 Java 代码。
## 验收标准

- `./gradlew build` 成功。
- 每个启用的平台模块都成功构建。
- Fabric 和 NeoForge 客户端都能启动，没有 Mixin、资源或模组加载错误。
-其他说明

完成后更新本 README 的功能描述，使其符合最终实现，并在最终报告中列出修改的文件、构建结果和无法完成的运行测试。再次检查所有代码是否符合 `AGENTS.md` 和 `OLD_AGENTS`的版本、映射和跨平台要求。
(主要看`OLD_AGENTS`)
