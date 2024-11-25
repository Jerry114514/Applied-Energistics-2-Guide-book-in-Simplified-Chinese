[![Build master](https://img.shields.io/github/actions/workflow/status/AppliedEnergistics/Applied-Energistics-2/build.yml?style=flat-square&branch=master)](https://github.com/AppliedEnergistics/Applied-Energistics-2/actions?query=workflow%3A%22Build+master%22)
[![Latest Release](https://img.shields.io/github/v/release/AppliedEnergistics/Applied-Energistics-2?style=flat-square&label=Release)](https://github.com/AppliedEnergistics/Applied-Energistics-2/releases)
[![Latest PreRelease](https://img.shields.io/github/v/release/AppliedEnergistics/Applied-Energistics-2?include_prereleases&style=flat-square&label=Pre)](https://github.com/AppliedEnergistics/Applied-Energistics-2/releases)

# 应用能源2 （又称AE2）

* 本项目（即本仓库）是Jerry Jiang @Jerry114514 的个人汉化项目，仓库内所有文件皆来自于AE2官方在github上开源的MD文档。  

* 因为所有文档皆以Markdown语法写成，若您能经常访问GitHub，建议复刻（Fork）到自己的库里，直接通过GitHub网页阅读，或下载其他的Markdown阅读器以便阅读。  

* 关于游戏内指南书的部分，请查阅位于 `guidebook` 文件夹内的 .md 文件，您正在阅读的此处文本是针对AE2项目自带的自读文件的汉化。  

* 本项目所翻译之文档仅适用于 Minecraft 1.20.1 版本的AE2模组，若您希望将这些内容应用至其他版本的AE2，请先与官方发布的对应版本的文档进行校对。

* 若您是第一次阅读该文档，请先阅读 `guidebook` 文件夹内的 `读前须知.md`。

## 

* [关于](#about)
* [联系我们](#contacts)
* [许可与声明](#license)
* [下载方式](#downloads)
* [安装](#installation)
* [报告问题](#issues)
* [API接口](#applied-energistics-2-api)
* [构建](#building)
* [贡献](#contribution)
* [本地化](#applied-energistics-2-localization)
* [开发人员](#credits)

## 简介

这是一个与物质和能源关联，并依靠这些去征服世界的模组...

## 联系我们

* [官方网站](https://appliedenergistics.org/)
* [玩家指南](https://guide.appliedenergistics.org/)
* [Discord 服务器链接](https://discord.gg/Zd6t9ka7ne)
* [GitHub 仓库](https://github.com/AppliedEnergistics/Applied-Energistics-2)

## 许可与声明

* Applied Energistics 2 API
  - (c) 2013 - 2020 AlgorithmX2 et al
  - [![License](https://img.shields.io/badge/License-MIT-red.svg?style=flat-square)](http://opensource.org/licenses/MIT)
* Applied Energistics 2
  - (c) 2013 - 2020 AlgorithmX2 et al
  - [![License](https://img.shields.io/badge/License-LGPLv3-blue.svg?style=flat-square)](https://raw.githubusercontent.com/AppliedEnergistics/Applied-Energistics-2/rv2/LICENSE)
* Textures and Models
  - (c) 2020, [Ridanisaurus Rid](https://github.com/Ridanisaurus/), (c) 2013 - 2020 AlgorithmX2 et al
  - [![License](https://img.shields.io/badge/License-CC%20BY--NC--SA%203.0-yellow.svg?style=flat-square)](https://creativecommons.org/licenses/by-nc-sa/3.0/)
* Text and Translations
  - [![License](https://img.shields.io/badge/License-No%20Restriction-green.svg?style=flat-square)](https://creativecommons.org/publicdomain/zero/1.0/)
* Additional Sound Licenses
  - Guidebook Click Sound
    - [EminYILDIRIM](https://freesound.org/people/EminYILDIRIM/sounds/536108/) 
    - [![License](https://img.shields.io/badge/License-CC%20BY%204.0-yellow.svg?style=flat-square)](https://creativecommons.org/licenses/by/4.0/)

## 下载方式

您可前往 CurseForge [点此前往CurseForge](https://www.curseforge.com/minecraft/mc-mods/applied-energistics-2) 或我们的官方网站 [点此前往应用能源2 官网](https://appliedenergistics.github.io/download)下载此模组。

## 安装

您可以通过将该模组的.jar文件放入 “minecraft/mods/” 文件夹来安装此模组。它没有额外的硬依赖关系。

## 报告问题

*（该部分建议您拥有使用Github或任何远程代码托管平台的经验）  

**（Github并未提供完整的简体中文支持，因此下文的部分内容会使用网页上的英文原文）  

针对应用能源2的崩溃，建议，或发现BUG？创建一个新的Issue吧！  


1.确保您的问题尚未得到回答或修复，并且您使用的是最新版本。在提交之前，还要考虑您的问题是否有效。  

*如果原版游戏和AE2本身已经可以实现，则该建议将被视为无效。  

*若您要求我们提供更小的版本、更紧凑的版本或更高效的版本，此类建议也将被视为无效。  

2.转到[Issues](https://github.com/AppliedEnergistics/Applied-Energistics-2/issues)然后单击[New Issues](https://github.com/AppliedEnergistics/Applied-Energistics-2/issues/new)。  

3.如果针对步骤1所要求的前提条件确认无误，请使用我们提供的模板之一。它还将包含有关所需或有用信息的更多详细信息。 
 
4.点击“Submit New Issue”，等待反馈！  

提供尽可能多的细节确实有助于我们更快地发现和解决问题，也有助于您尽快获修复后的版本。  

请注意，我们可能会关闭任何不符合这些要求的问题。  

## 应用能源2 API接口  

以下是应用能源2的接口，它们皆是开源的，可以讨论更改、改进文档并提供更好的附加组件支持。  
（译者实力有限，下文不翻译了）  

### Maven

Our authoritative Maven repository is Github Packages, which you can also use in your builds. Use of Github Packages 
[requires special setup](https://docs.github.com/en/packages/using-github-packages-with-your-projects-ecosystem/configuring-gradle-for-use-with-github-packages#authenticating-to-github-packages) 
to authenticate with your personal access token.

AE2 is also available without authentication from Modmaven. You can use the following snippet as example on how to add a repository to your gradle build file.

    repositories {
        maven {
            name "Modmaven"
            url "https://modmaven.dev/"
            // For Gradle 5.1 and above, limit it to just AE2
            content {
                includeGroup 'appeng'
            }
        }
    }

When compiling against the AE2 API you can use gradle dependencies, just add

    dependencies {
        modCompileOnly "appeng:appliedenergistics2-fabric:VERSION:api"
    }

or add the `modCompileOnly` line to your existing dependencies task to your build.gradle.

Replace `VERSION` with the desired one. With 1.15+ we switched to using [semver](https://semver.org/). 
It is highly recommended following its specification and further considering an upper bound for the dependency version.
A change of the `MAJOR` version will be an API break and can lead to various crashes. Better to inform a player about the addon not supporting the new version until it could be tested or updated.

An example string would be `appeng:appliedenergistics2-fabric:12.9.5:api` for the API only or `appeng:appliedenergistics2-fabric:12.9.5` for the whole mod.

## 构建

1. 通过以下方式克隆AE2的仓库  
  - SSH `git clone git@github.com:AppliedEnergistics/Applied-Energistics-2.git` 或  
  - HTTPS `git clone https://github.com/AppliedEnergistics/Applied-Energistics-2.git`  
2. 使用 `gradlew runData build` 命令来构建仓库. .jar 文件将会被储存在 `build/libs` 中。  
3. 开发人员看此: Setup IDE  
  - IntelliJ: Import as gradle project  
  - Eclipse: Import as gradle project or execute gradle task `eclipse` and potentially `genEclipseRuns`  

## 贡献

在您想添加重大更改之前，您可能想先与我们讨论一下，以避免浪费时间。  
如果你仍然愿意为这个项目做出贡献，你可以通过 [Pull Request] 做出贡献(https://help.github.com/articles/creating-a-pull-request).  

[贡献指南](https://github.com/AppliedEnergistics/Applied-Energistics-2/blob/master/.github/CONTRIBUTING.md)包含有关所用代码样式等主题的更详细信息，也应予以考虑。  

以下是一些需要记住的事情，这将有助于你的PR获得批准。  

*PR应该注重内容。任何仅更改语法的PR都将被拒绝。  
*将您正在编辑的文件用作样式指南。  
*考虑一下你的特点。  
-您的建议是否已经可以用于原版游戏+AE2？  
-确保你的功能尚未开发，或者之前没有被拒绝。  
-您的功能是否简化了AE2的另一个功能？这些更改将不被接受。  
-如果你的功能可以通过任何流行的模组完成，请先与我们讨论。  

**新手上路**

（其实用Github Desktop更简单了）  
1. 创建一个AE2的复刻（Fork）。  
2. 通过以下方式之一克隆该复刻：  
  * SSH `git clone git@github.com:<your username>/Applied-Energistics-2.git` 或   
  * HTTPS `git clone https://github.com/<your username>/Applied-Energistics-2.git`。  
3. 更改代码库。  
4. 运行`gradlew spotlessApply`以应用自动代码格式化。  
5. 若欲向git提交更改，使用 `git add -A`。  
6. 确认提交更改至克隆库，使用 `git commit -m "<summary of made changes>"`  
7. 推送更新到复刻库，使用 `git push`。  
8. 在Github上提交PR。  
9. 等待审核。  
10. Squash commits for cleaner history。（？）  

如果你只做单文件拉取请求，GitHub支持使用一种快速的方法，而不需要克隆你的fork。另请阅读[同步复刻](https://docs.github.com/zh/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork)如果你打算定期做出贡献。  

## 应用能源2 本地化

### 简体中文

`zh_CN` 的指南书部分由[@Jerry114514]翻译。[B站账号](https://space.bilibili.com/57439297)

### 英语文本

`en_US` 已包含在本仓库中, 欢迎修正拼写错误.

### 编码

文件必须以UTF-8格式编码。

### 新的/更新 翻译文件

我们使用Crowdin众包翻译进行本地化。您可以在我们的[Crowdin页面](https://appliedenergistics2.crowdin.com/applied-energistics-2)上参与应用能源2的本地化。 

请记住，我们使用[String格式](https://docs.oracle.com/javase/8/docs/api/java/util/Formatter.html)将附加数据传递给文本以供显示。  
因此，您应该保留像“%s”或“%1$d%%”这样的部分，这样我们就可以用正确的值替换它们，同时您仍然可以选择更改它们的顺序以匹配对应语言的语法。  
对于某些语言来说，这可能是不可能的。如果是这样的话，请联系我们。  

### 结语

如果您在本地化方面有任何问题，请随时通过IRC联系我们，网址为Esper.net上的#AppliedEnergys。  

感谢大家帮助改进AE2的本地化。  

## 开发人员

感谢以下人员/组织/项目:

* Notch et al for Minecraft  
* Lex et al for MinecraftForge  
* AlgorithmX2 for AppliedEnergistics2  
* [Ridanisaurus Rid](https://github.com/Ridanisaurus/) 制作的 2020 份新材质 
* 所有的 [贡献者们](https://github.com/AppliedEnergistics/Applied-Energistics-2/graphs/contributors)  
