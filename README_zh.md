[![Build master](https://img.shields.io/github/actions/workflow/status/AppliedEnergistics/Applied-Energistics-2/build.yml?style=flat-square&branch=master)](https://github.com/AppliedEnergistics/Applied-Energistics-2/actions?query=workflow%3A%22Build+master%22)
[![Latest Release](https://img.shields.io/github/v/release/AppliedEnergistics/Applied-Energistics-2?style=flat-square&label=Release)](https://github.com/AppliedEnergistics/Applied-Energistics-2/releases)
[![Latest PreRelease](https://img.shields.io/github/v/release/AppliedEnergistics/Applied-Energistics-2?include_prereleases&style=flat-square&label=Pre)](https://github.com/AppliedEnergistics/Applied-Energistics-2/releases)
[![Maven Central Version](https://img.shields.io/maven-central/v/org.appliedenergistics/appliedenergistics2)](https://central.sonatype.com/artifact/org.appliedenergistics/appliedenergistics2)

# 应用能源 2

## 目录

* [简介](#简介)
* [联系方式](#联系方式)
* [许可证](#许可证)
* [下载](#下载)
* [安装](#安装)
* [问题反馈](#问题反馈)
* [API](#应用能源2-api)
* [构建](#构建)
* [贡献](#贡献)
* [本地化](#应用能源2-本地化)
* [鸣谢](#鸣谢)

## 简介

一个关于物质、能量以及利用它们征服世界的Minecraft模组...

## 联系方式

* [官网](https://appliedenergistics.org/)
* [玩家指南](https://guide.appliedenergistics.org/)
* [Discord](https://discord.gg/Zd6t9ka7ne)
* [GitHub](https://github.com/AppliedEnergistics/Applied-Energistics-2)

## 许可证

* 应用能源 2 API
  - (c) 2013 - 2020 AlgorithmX2 等
  - [![License](https://img.shields.io/badge/License-MIT-red.svg?style=flat-square)](http://opensource.org/licenses/MIT)
* 应用能源 2
  - (c) 2013 - 2020 AlgorithmX2 等
  - [![License](https://img.shields.io/badge/License-LGPLv3-blue.svg?style=flat-square)](https://raw.githubusercontent.com/AppliedEnergistics/Applied-Energistics-2/rv2/LICENSE)
* 材质与模型
  - (c) 2020, [Ridanisaurus Rid](https://github.com/Ridanisaurus/), (c) 2013 - 2020 AlgorithmX2 等
  - [![License](https://img.shields.io/badge/License-CC%20BY--NC--SA%203.0-yellow.svg?style=flat-square)](https://creativecommons.org/licenses/by-nc-sa/3.0/)
* 文本与翻译
  - [![License](https://img.shields.io/badge/License-No%20Restriction-green.svg?style=flat-square)](https://creativecommons.org/publicdomain/zero/1.0/)
* 附加音效许可证
  - 指南书点击音效
    - [EminYILDIRIM](https://freesound.org/people/EminYILDIRIM/sounds/536108/)
    - [![License](https://img.shields.io/badge/License-CC%20BY%204.0-yellow.svg?style=flat-square)](https://creativecommons.org/licenses/by/4.0/)

## 下载

你可以在 [CurseForge](https://www.curseforge.com/minecraft/mc-mods/applied-energistics-2)、[Modrinth](https://modrinth.com/mod/ae2) 或 [官网](https://appliedenergistics.github.io/download) 下载。

## 安装

将模组放入 `minecraft/mods/` 文件夹即可安装。它没有额外的硬性依赖。

## 问题反馈

应用能源2崩溃、有建议或发现bug？立即创建issue！

1. 确保你的问题没有被回答或修复，并且你使用的是最新版本。提交前请确认你的问题是否有效。
    - 如果使用原版和AE2本身已经可以做到，该建议将被视为无效。
    - 要求更小、更紧凑或更高效版本的内容也将被视为无效。
2. 进入 [issues页面](https://github.com/AppliedEnergistics/Applied-Energistics-2/issues) 并点击 [new issue](https://github.com/AppliedEnergistics/Applied-Energistics-2/issues/new)
3. 如果适用，请使用提供的模板。它会包含关于所需或有用信息的更多细节。
4. 点击 `Submit New Issue`，等待反馈！

提供尽可能多的详细信息有助于我们更快地找到和解决问题，你也能更快地获得修复版本。

请注意，不符合这些要求的issue可能会被关闭。

## 应用能源2 API

应用能源2的API。开源此API是为了讨论变更、改进文档，以及 generally提供更好的附加模组支持。

### Maven

AE2可在 [Maven Central](https://central.sonatype.com/artifact/org.appliedenergistics/appliedenergistics2) 获取。

以下是如何在gradle构建文件中添加仓库的示例。

    repositories {
        mavenCentral()
    }

我们也在Github Packages上有发布，你也可以在构建中使用。使用Github Packages需要[特殊设置](https://docs.github.com/en/packages/using-github-packages-with-your-projects-ecosystem/configuring-gradle-for-use-with-github-packages#authenticating-to-github-packages)来用你的个人访问令牌进行认证。

编译AE2 API时，你可以使用gradle依赖，只需添加

    dependencies {
        compileOnly "org.appliedenergistics:appliedenergistics2:VERSION:api"
    }

或将 `compileOnly` 行添加到你的build.gradle的现有依赖块中。

将 `VERSION` 替换为你需要的版本。从1.15+开始我们改用 [semver](https://semver.org/)。

强烈建议遵循其规范并考虑为依赖版本设置上限。

`MAJOR` 版本的变更将导致API破坏，可能导致各种崩溃。最好通知玩家附加模组不支持新版本，直到它可以被测试或更新。

一个示例字符串是 `org.appliedenergistics:appliedenergistics2:12.9.5:api` 用于仅获取API，或 `org.appliedenergistics:appliedenergistics2:12.9.5` 用于整个模组。

## 构建

1. 通过以下方式克隆此仓库
   - SSH `git clone git@github.com:AppliedEnergistics/Applied-Energistics-2.git` 或
   - HTTPS `git clone https://github.com/AppliedEnergistics/Applied-Energistics-2.git`
2. 使用 `gradlew runData build` 命令构建。JAR文件将在 `build/libs` 中
3. 对于核心开发者：在IDE中加载Gradle项目

## 贡献

在你想进行重大修改之前，可能想先和我们讨论，以免浪费你的时间。

如果你仍然愿意为这个项目做贡献，你可以通过 [Pull-Request](https://help.github.com/articles/creating-a-pull-request) 贡献。

[贡献指南](https://github.com/AppliedEnergistics/Applied-Energistics-2/blob/master/.github/CONTRIBUTING.md) 包含了关于使用的代码风格等更详细的信息，也应该被考虑。

以下是一些有助于让你的PR被接受的注意事项。

* PR应该专注于内容。任何只改变语法的PR都将被拒绝。
* 使用你正在编辑的文件作为风格指南。
* 考虑你的功能。
  - 你的建议是否已经可以用原版+AE2实现？
  - 确保你的功能不在进行中或之前被拒绝。
  - 你的功能是否简化了AE2的另一个功能？这些更改将不会被接受。
  - 如果你的功能可以由任何流行模组完成，请先与我们讨论。

**入门指南**

1. Fork此仓库
2. 克隆你的fork
   * SSH `git clone git@github.com:<你的用户名>/Applied-Energistics-2.git` 或
   * HTTPS `git clone https://github.com/<你的用户名>/Applied-Energistics-2.git`
3. 修改代码
4. 运行 `gradlew spotlessApply` 应用自动代码格式化
5. 将更改添加到git `git add -A`
6. 提交到你的克隆 `git commit -m "<更改摘要>"`
7. 推送到你的fork `git push`
8. 在GitHub上创建Pull-Request
9. 等待审核
10. 压缩提交以获得更干净的历史

如果你只做单文件pull requests，GitHub支持一种不需要克隆你的fork的快捷方式。如果你计划定期贡献，也请阅读关于[同步](https://help.github.com/articles/syncing-a-fork)的内容。

## 应用能源2 本地化

### 英文文本

`en_US` 已包含在此仓库中，欢迎修复拼写错误。

### 编码

文件必须编码为UTF-8。

### 新增或更新翻译

我们使用Crowdin众包翻译进行本地化。你可以在我们的 [Crowdin页面](https://appliedenergistics2.crowdin.com/applied-energistics-2) 参与应用能源2的本地化。

请记住，我们使用 [String format](https://docs.oracle.com/javase/8/docs/api/java/util/Formatter.html) 来传递额外数据到文本以进行显示。

因此你应该保留 `%s` 或 `%1$d%%` 这样的部分，这允许我们在保持更改顺序以匹配语法规则的同时替换正确的值。

对于某些语言这可能不可能。如果是这种情况，请联系我们。

### 最后说明

如果在本地化过程中遇到问题，请随时在 [Discord](https://discord.gg/b6HZ4p8EKH) 上联系我们。

感谢所有帮助改进AE2本地化的人。

## 鸣谢

感谢我们的所有 [贡献者](https://github.com/AppliedEnergistics/Applied-Energistics-2/graphs/contributors)！
