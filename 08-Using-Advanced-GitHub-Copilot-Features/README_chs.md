<header>

# 使用 GitHub Copilot 高级功能

GitHub Copilot 不仅仅是代码建议。作为一名软件工程师，你经常会发现自己需要理解现有代码，并通过文档、测试和自动化来增强它。

在本模块中，你将使用 GitHub Copilot 的高级功能，这将允许你以互动方式处理代码并高效地应用建议和知识。

你将使用基于 Python 的现有 HTTP API 进行更改、修复错误、编写文档和测试新端点。

</header>

- **适合人群**: 开发人员、DevOps 工程师、软件开发经理、测试人员。
- **你将学到什么**: 使用 GitHub Copilot 高级功能来测试、记录和处理代码。
- **你将构建什么**: 一个新的 HTTP API 路由，以及验证其正确性的文档和测试。
- **先决条件**: 要使用 GitHub Copilot，你必须有一个有效的 GitHub Copilot 订阅。注册 30 天免费 [Copilot](https://github.com/settings/copilot)。
- **时间**: 本模块可以在一小时内完成。

在本模块结束时，你将掌握以下技能：

- 使用高级 GitHub Copilot 功能，如内联聊天、斜杠命令和代理。
- 通过更深入的项目上下文与 GitHub Copilot 互动，并询问有关项目的问题。

## 预备阅读:
- [GitHub Copilot 提示工程入门](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot//?WT.mc_id=academic-113596-abartolo)
- [使用高级 GitHub Copilot 功能](https://learn.microsoft.com/training/modules/advanced-github-copilot/?WT.mc_id=academic-113596-abartolo)

## 要求

1. 启用您的 [GitHub Copilot 服务](https://github.com/github-copilot/signup)
2. 使用 Codespaces 打开 [此存储库](https://codespaces.new/MicrosoftDocs/mslearn-advanced-copilot)

## 💪🏽 练习

**右键单击以下 Codespaces 按钮以在新标签页中打开您的 Codespace**
 
[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-python)

当前 API 没有透露 country/{country} 端点，需要实现这个以列出城市的端点。该路由应仅允许 GET HTTP 请求，并提供以 JSON 响应包含该国家、城市和给定月份的历史最高和最低信息。

与任何实现一样，此添加应包含至少一个测试函数，以使用 pytest 运行器和测试框架进行工作。

### 🛠 步骤 1: 添加一个新路由
在我们的第一个练习中，我们将在我们的 API 中创建一个新的路由。转到 main.py 文件，并使用以下命令 `ctrl` + `i` (在 Windows 上) 或 `cmd` + `i` (在 Mac 上) 通过内联聊天询问 GitHub Copilot 帮助你创建一个显示国家城市的新 API。

在内联聊天中使用以下提示：

```
Create a new route that exposes the cities of a country.
```

此提示应为你提供类似如下内容：

```python
# 创建一个揭露国家城市的新路由：
@app.get('/countries/{country}')
def cities(country: str):
    return list(data[country].keys())
```

> [!NOTE]
> 尝试新的路由并优化提示，直到结果满足需求。

### 🔎 步骤 2: 创建一个测试
现在你已创建了一个新的路由，让我们使用 Copilot Chat 为这个路由创建一个使用西班牙作为国家的测试。记住选择你的代码，并询问 Copilot Chat 帮助你完成我们刚刚创建的特定 API 的测试。

在 GitHub Copilot Chat 中使用以下提示：

```
/tests help me to create a new test for this route that uses Spain as the country.
```

![Copilot Chat 示例图像](https://raw.githubusercontent.com/MicrosoftDocs/mslearn-advanced-copilot/main/images/ideascopilot.png)

一旦 Copilot 帮助你创建了测试，请尝试它。如果它没有按预期运行，不妨在聊天中分享这些细节。例如：

```
This test is not quite right, it is not including cities that doesn't exist. Only Seville is part of the API.
```

它应为您提供另一个解决方案。继续尝试，直到达到期望的结果。

### 🐍 步骤 3: 使用代理编写项目
在此步骤中，我们将使用代理（工作空间）编写有关如何运行此项目的项目文档。在 GitHub Copilot Chat 中，我们将尝试以下提示：

`> @workspace help me to use an agent to write the project documentation on how to run it .`

最后，通过转到 `/docs` 端点并确认端点显示出来，验证新端点是否工作。

### 💡 步骤 4: 使用斜杠命令

现在你已经使用 GitHub Copilot 生成和解释了代码，你还可以探索其他一些方法来执行开发者任务。这些额外的挑战将帮助你更深入地了解除你已知的 GitHub Copilot 功能之外的其他功能。对于这些额外的挑战，您将使用 Chat 界面。如果还没有打开，请单击左侧边栏上的 GitHub Copilot Chat 图标。

🚀 恭喜你，通过这个练习，你已经使用了 GitHub Copilot 的许多不同功能，从而可以更好地处理不同项目。你使用了一些功能来书写测试、文档，并了解现有代码。

## 法律声明

Microsoft 和任何贡献者授予您在本存储库中的 Microsoft 文档和其他内容的许可，符合 [知识共享署名 4.0 国际公共许可协议](https://creativecommons.org/licenses/by/4.0/legalcode)，详见 [LICENSE](LICENSE) 文件，并授予您在存储库中的任何代码的许可，符合 [MIT 许可证](https://opensource.org/licenses/MIT)，详见 [LICENSE-CODE](LICENSE-CODE) 文件。

Microsoft、Windows、Microsoft Azure 和/或本文档中提到的其他 Microsoft 产品和服务可能是 Microsoft 在美国和/或其他国家/地区的商标或注册商标。本项目的许可不授予您使用任何 Microsoft 名称、标识或商标的权利。Microsoft 的一般商标指南可在 http://go.microsoft.com/fwlink/?LinkID=254653 查阅。

隐私信息可在 https://privacy.microsoft.com/zh-cn/ 查阅。

Microsoft 和任何贡献者保留所有其他权利，无论是根据各自的版权、专利或商标，还是通过暗示、禁止反言或其他方式。