<header>

# GitHub Codespaces 介绍

欢迎进入 GitHub Codespaces 的精彩世界，这是一个基于云的编码资源。在本模块中，我们将深入探索即时的、基于云的开发环境，彻底改变你编写代码的方式。GitHub Codespaces 提供了无缝集成的体验，它提供了一个容器，配备了开发所需的基础语言、工具和实用程序。

在整个学习过程中，我们将探索 Codespaces 的生命周期和流程。揭示定制你的 Codespace 设置以适应你的特殊偏好和需求的力量。为了巩固你的理解，我们将以一个实践练习结束本模块，让你在 GitHub Codespaces 环境中展示你的编码能力。

想象一下，一个完全配置好的开发环境，就在你指尖上，可以从任何有互联网连接的电脑上访问。GitHub Codespaces 开启了一个新合作和灵活编码的时代。让我们一起深入探索并充分挖掘 GitHub Codespaces 基于云开发的潜力吧！

</header>

- **适合人群**: 开发者、DevOps 工程师、工程经理、产品经理。
- **你将学会**: 如何创建 codespace、从 codespace 推送代码、选择自定义镜像以及定制 codespace。
- **你将构建**: 一个带有 devcontainer.json 文件、自定义设置和个性化设置的 codespace。
- **先决条件**: 你需要掌握以下内容:
  - 使用 Visual Studio Code，[Visual Studio Code 文档](https://code.visualstudio.com/docs)。
  - 了解 GitHub 的使用或完成上一模块 [GitHub 介绍](https://github.com/WirelessLife/Mastering-GitHub-Copilot-for-Paired-Programming/blob/main/01-Introduction-to-GitHub/README.md?WT.mc_id=academic-113596-abartolo)。
- **时长**: 本课程可以在一小时内完成。

在本模块结束时，你将能够:

1. 描述 GitHub Codespaces。
2. 解释 GitHub Codespace 生命周期及如何完成每一步。
3. 定义可以在 GitHub Codespaces 中个性化的不同自定义选项。

## 先决条件阅读:

- [使用 GitHub Codespaces 编码](https://learn.microsoft.com/training/modules/code-with-github-codespaces/?WT.mc_id=academic-113596-abartolo)
- 什么是 GitHub Codespaces？（如下视频播放列表）
- [![什么是 Codespaces](https://img.youtube.com/vi/ozuDPmcC1io/0.jpg)](https://www.youtube.com/watch?v=ozuDPmcC1io&list=PLmsFUfdnGr3wTl-NCblzcrEv2lFSX975-)

### 如何开始本课程

<!-- 要开始课程，在 JavaScript 中运行:
'https://github.com/new?' + new URLSearchParams({
  template_owner: 'skills',
  template_name: 'code-with-codespaces',
  owner: '@me',
  name: 'skills-code-with-codespaces',
  description: 'My clone repository',
  visibility: 'public',
}).toString()
-->

[![开始课程](https://user-images.githubusercontent.com/1221423/235727646-4a590299-ffe5-480d-8cd5-8194ea184546.svg)](https://github.com/new?template_owner=skills&template_name=code-with-codespaces&owner=%40me&name=skills-code-with-codespaces&description=My+clone+repository&visibility=public)

1. 右键点击 **开始课程** 并在新标签页中打开链接。
2. 在新标签页中，大部分提示会为你自动填写。
   - 对于所有者，选择你的个人账户或组织来托管代码库。
   - 我们建议创建公共代码库，因为私有代码库会[使用 Actions 运行时间](https://docs.github.com/en/billing/managing-billing-for-github-actions/about-billing-for-github-actions?WT.mc_id=academic-113596-abartolo)。
   - 向下滚动并点击表单底部的 **创建代码库** 按钮。
3. 创建新代码库后，等待大约 20 秒，然后刷新页面。按照新代码库 README 中的分步说明进行操作。

<footer>

<!--
  <<< 作者注释: 页脚 >>>
  添加获取支持的链接、GitHub 状态页面、行为守则、许可证链接。
-->

---

获取帮助: [在我们的讨论板中发帖](https://github.com/orgs/skills/discussions/categories/introduction-to-github) &bull; [查看 GitHub 状态页面](https://www.githubstatus.com/)
