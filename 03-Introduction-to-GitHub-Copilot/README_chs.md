<header>

# 介绍 GitHub Copilot

在这个学习模块中，我们将深入探讨 AI 配对编程的创新领域，了解 GitHub Copilot，这款首个大规模 AI 开发者工具，旨在提升您的编码体验。

GitHub Copilot 会从文件和评论中分析上下文，并从其交互式聊天中获取输入，提供自动完成样式的建议，使您能够更快、更轻松地编写代码。随着您深入学习这个模块，您将全面了解 GitHub Copilot 的复杂性，探索其在 VS Code 和 Codespaces 中的功能。

我们的学习目标宏大但切实可行。在模块结束时，您不仅能够阐述 GitHub Copilot 是什么及其优势，还能理解它对个人和企业的适用性。了解 GitHub Copilot 的未来，并通过动手练习掌握如何使用它与 Visual Studio Code 进行开发。

研究表明，GitHub Copilot 使开发人员能够更快地编写代码，专注于解决重大问题，保持更长时间的工作效率，并在工作中体验更大的满足感。


注意：虽然此模块使用 [Codespaces](https://github.com/codespaces)，但您可以在包括本地 Visual Studio Code 在内的多种其他环境中使用 GitHub Copilot。
</header>


- **适用对象**：开发人员，DevOps 工程师，软件开发经理，测试人员。
- **您将学习到**：如何在 Codespace 中安装 Copilot，接受代码建议，接受评论建议。
- **您将构建**：由 Copilot AI 生成代码和评论建议的 JavaScript 文件。
- **前提条件**：要使用 GitHub Copilot，您必须拥有一个有效的 GitHub Copilot 订阅。注册 30 天免费试用 [Copilot](https://github.com/settings/copilot)。
- **时间安排**：本课程可在一小时内完成。


在这个模块的结尾，您将能够：

- 解释 GitHub Copilot 是什么及其提供的优势。
- 了解 GitHub Copilot 对个人和企业的适用性。
- 讨论 GitHub Copilot 的未来。
- 学习如何开始使用 GitHub Copilot 及其一些常见配置。
- 通过动手练习使用 Visual Studio Code 开发 GitHub Copilot。


## 前提阅读:
- [介绍 GitHub Copilot](https://learn.microsoft.com/en-us/training/modules/introduction-to-github-copilot/?WT.mc_id=academic-113596-abartolo)
- 什么是 GitHub Copilot？（以下视频播放列表）
- [![What is GitHub Copilot](https://img.youtube.com/vi/QG1E0SCqqW8/0.jpg)](https://learn.microsoft.com/shows/introduction-to-github-copilot/what-is-github-copilot-1-of-6/?WT.mc_id=academic-113596-abartolo)

### 如何开始本课程

<!-- For start course, run in JavaScript:
'https://github.com/new?' + new URLSearchParams({
  template_owner: 'skills',
  template_name: 'copilot-codespaces-vscode',
  owner: '@me',
  name: 'skills-copilot-codespaces-vscode',
  description: 'My clone repository',
  visibility: 'public',
}).toString()
-->

[![start-course](https://user-images.githubusercontent.com/1221423/235727646-4a590299-ffe5-480d-8cd5-8194ea184546.svg)](https://github.com/new?template_owner=skills&template_name=copilot-codespaces-vscode&owner=%40me&name=skills-copilot-codespaces-vscode&description=My+clone+repository&visibility=public)

1. 右键单击 **开始课程** 并在新标签页中打开链接。
2. 在新标签页中，大部分提示将自动为您填充。
   - 对于所有者，选择您的个人帐户或一个组织来托管存储库。
   - 我们建议创建一个公共存储库，因为私有存储库将[使用 Actions 分钟](https://docs.github.com/en/billing/managing-billing-for-github-actions/about-billing-for-github-actions)。
   - 向下滚动并单击表单底部的 **创建存储库** 按钮。
3. 创建新存储库后，等待大约 20 秒，然后刷新页面。按照新存储库的 README 中的分步说明进行操作。

<footer>

<!--
  <<< Author notes: Footer >>>
  Add a link to get support, GitHub status page, code of conduct, license link.
-->

---

获取帮助: [在我们的讨论板中发帖](https://github.com/orgs/skills/discussions/categories/code-with-copilot) &bull; [查看 GitHub 状态页面](https://www.githubstatus.com/)
</footer>