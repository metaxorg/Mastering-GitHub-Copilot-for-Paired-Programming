<header>

# 使用GitHub Copilot与Python开发

GitHub Copilot是全球首款大规模AI开发工具，通过在您工作时提供自动完成风格的建议，大大加快了编写代码的速度。在本模块中，我们将重点使用GitHub Copilot的强大功能来提高您的Python编码效率。

作为开发人员，您的目标是提高生产力并加快编码过程。GitHub Copilot就像是您的AI编程搭档，根据上下文和代码模式提供建议。在本模块中，您将使用GitHub Copilot和Codespaces有效生成和实现代码建议。

准备好投入到一个真实的场景中吧！您将修改一个Python仓库，使用GitHub Copilot创建一个交互式HTML表单和一个API端点。本项目将为您提供开发提供HTTP API的Python Web应用程序的宝贵经验，生成用于识别目的的伪随机令牌。

</header>


- **目标人群**: 开发人员，DevOps工程师，软件开发经理，测试人员。
- **您将学到的内容**: 使用GitHub Copilot创建代码并为您的工作添加注释。
- **您将构建的内容**: 包含由Copilot AI生成代码和注释建议的Python文件。
- **先决条件**: 要使用GitHub Copilot，您必须订阅一个有效的GitHub Copilot订阅。注册获取30天免费试用 [Copilot](https://github.com/settings/copilot)。
- **时间**: 该模块可在一小时内完成。

在本模块结束时，您将掌握以下技能:

- 精心设计提示以从GitHub Copilot生成建议
- 使用GitHub Copilot改进您的项目。

## 必读内容:
- [GitHub Copilot提示工程简介](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot//?WT.mc_id=academic-113596-abartolo)
- [使用GitHub Copilot与Python](https://learn.microsoft.com/en-us/training/modules/introduction-copilot-python/?WT.mc_id=academic-113596-abartolo)

## 要求

1. 启用您的[GitHub Copilot服务](https://github.com/github-copilot/signup)
1. 使用Codespaces打开[此仓库](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-python)

## 💪🏽 练习

**右键点击下方的Codespaces按钮在新标签页中打开您的Codespace**
 
[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-python)

API已经有一个生成令牌的端点。让我们通过添加一个新的端点来更新API，该端点接受文本并返回令牌列表。

### 🛠 步骤1: 添加一个Pydantic模型

转到`main.py`文件，导航到提供的代码底部，选择**Ctrl + I(PC)**或**Cmd + I(Mac)**，并将以下内容复制到提供的GitHub Copilot聊天框中以便为您生成一个`Pydantic`模型：

```
Create a Pydantic model so that I can use it in a new route that will accept JSON with text as a key which accepts a string.
```

生成的模型应如下所示：

```python
    class TextData(BaseModel):
        text: str
```

> [!注意]
> 您可能会在编辑器中看到一些识别的(带红点虚线下划线)linter警告，可以忽略。这些包括长行或甚至是不需要的新行。如果您愿意，可以解决它们，尽管这些不应影响您的应用程序的正常运行。

### 🔎 步骤2: 生成一个新端点

接下来，通过在`main.py`文件的最后一个路由下添加注释，使用GitHub Copilot生成一个新的端点。

```python
# Create a FastAPI endpoint that accepts a POST request with a JSON body containing a single field called "text" and returns a checksum of the text
```

您可能会得到一个使用未导入的模块或库的建议。如果是这样，可以通过选择生成的代码，并使用Command+I（苹果）或Control+I（Windows），添加一个提示来帮助您导入缺少的模块。此小弹出窗口称为内联聊天，是与GitHub Copilot互动的另一种方式。

### 🐍 步骤3: 解释代码

`generate()`路由使用一行代码创建一个伪随机令牌ID，可能很难完全理解。选择整个函数，然后右键单击选择内容，在Copilot菜单项中选择_"解释此"_选项。GitHub Copilot聊天界面将打开左侧窗口，并提供有用的解释，您可以用它来互动式的提问更多问题。

最后，通过访问`/docs`端点并确认新端点显示出来，验证新端点是否工作。

🚀 恭喜您，通过练习，您不仅使用Copilot生成了代码，而且以一种互动和有趣的方式完成了它！您可以使用GitHub Copilot不仅生成代码，还可以编写文档，测试您的应用程序等。

### 💡 步骤4: 使用Slash命令

现在您已经使用GitHub Copilot生成并解释了代码，您还可以探索一些替代方法来执行开发者任务。这些额外的挑战将帮助您深入了解除已经掌握的以外的其他GitHub Copilot功能。对于这些额外的挑战，您将使用聊天界面。如果尚未打开，单击左侧栏中的GitHub Copilot聊天图标。

**生成文档**
 
打开`main.py`，使用聊天界面并使用以下文本：

```
/docs I need to document the routes for these API Routes. Help me produce documentation I can put in the README.md file of this project
```

提示中的`/docs`部分称为_“斜杠命令”_，这是GitHub Copilot的一个特定功能，允许您编写文档。如果结果看起来不错，请将它们添加到此项目的README.md文件的新部分中。

**生成测试**
 
当前代码没有任何测试。对于这个挑战，您将使用`/tests`斜杠命令。打开`main.py`，使用聊天界面并使用以下提示：

```
/tests help me write a test for the generate() route using the FastAPI test client and the Pytest framework. Help me understand where I should put the test file, how to add the Pytest dependency to my project, and how to run the tests
```

`/tests`斜杠命令将引导您编写新的路由测试，并提供所有必需的内容，以便您可以验证您的工作。

**工作区挑战**
 
最后，您将有机会使用一个_代理人_。代理人是VS Code中GitHub Copilot的一项特殊功能，允许特定的上下文与GitHub Copilot共享。对于最后一个挑战，您将使用`@workspace`代理人，包括当前工作区的文件以提供更多上下文。您将解决一个与如何运行整个应用程序相关的问题。在此情况下，您将增强README.md以提供更多跨多个文件的具体信息。使用`@workspace`有助于提供更多上下文，而无需打开多个文件。

对于这个最终挑战，您无需打开任何文件。在GitHub Copilot聊天窗口中使用以下提示：

```
@workspace I want to provide instructions on how to run this application using the uvicorn webserver, I also need to provide instructions on how to install the dependencies properly and what are some characteristics of the FastAPI framework. I will use this to improve the README.md file
```

结果应为关于FastAPI如何运行应用程序以及如何安装依赖项的非常好的解释。响应顶部的报告可能包括所有引用，用于确定需要使用哪些文件以提供GitHub Copilot所需的正确上下文。

## 法律声明

Microsoft和任何贡献者授予您在本存储库中Microsoft文档和其他内容的许可，依据[知识共享署名4.0国际公共许可证](https://creativecommons.org/licenses/by/4.0/legalcode)，请参阅[LICENSE](LICENSE)文件，并授予您在存储库中的任何代码的许可，依据[MIT许可证](https://opensource.org/licenses/MIT)，请参阅
[LICENSE-CODE](LICENSE-CODE)文件。

Microsoft、Windows、Microsoft Azure和/或文档中引用的其他Microsoft产品和服务可能是Microsoft在美国和/或其他国家的商标或注册商标。
本项目的许可证不授予您使用任何Microsoft名称、徽标或商标的权利。
Microsoft的一般商标指南可以在http://go.microsoft.com/fwlink/?LinkID=254653找到。

隐私信息可以在 https://privacy.microsoft.com/en-us/ 上找到。

Microsoft和任何贡献者保留所有其他权利，无论是否在各自的版权、专利、
或商标下，无论通过暗示、禁止反言或其他方式。