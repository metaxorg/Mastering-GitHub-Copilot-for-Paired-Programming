<header>

# 使用 GitHub Copilot 编写 C#

GitHub Copilot 是首个大规模的 AI 开发工具，通过提供类似自动完成的建议显著加快代码编写速度。在本模块中，我们将重点使用 GitHub Copilot 的强大功能以提升您的 C# 编码效率。

作为开发人员，您的目标是提高生产力并加快编码进程。GitHub Copilot 充当您的 AI 配对程序员，根据上下文和代码模式提出建议。在本模块结束时，您不仅将会学会如何在 Codespaces 中配置 GitHub Copilot，还将学会如何有效生成和实施代码建议。

准备好进入一个真实的场景吧！您将通过使用 GitHub Copilot 修改一个 C# 存储库以创建一个 API 端点，来获得宝贵的经验。本项目将让您在开发一个提供 HTTP API 的 C# 网络应用、生成伪随机天气预报信息中获得有益的实践。

</header>


- **适合对象**: 开发人员，DevOps 工程师，软件开发经理，测试人员
- **您将会学到**: 如何使用 GitHub Copilot 创建代码并为您的工作添加注释
- **您将会构建**: 具有由 Copilot AI 生成的代码和注释建议的 C# 文件
- **先决条件**: 要使用 GitHub Copilot，您必须拥有一个活跃的 GitHub Copilot 订阅。注册 30 天免费 [Copilot](https://github.com/settings/copilot).
- **时间**: 本课程可以在不到一小时内完成。

到本模块结束时，您将获得以下技能：

- 设计提示以从 GitHub Copilot 生成建议
- 应用 GitHub Copilot 改进您的项目

## 预备阅读:
- [GitHub Copilot 与提示工程入门](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot?WT.mc_id=academic-113596-abartolo)

- [什么是 Visual Studio 的 GitHub Copilot 扩展？](https://learn.microsoft.com/en-us/visualstudio/ide/visual-studio-github-copilot-extension?view=vs-2022&WT.mc_id=academic-113596-abartolo)

## 必要条件

1. 启用您的 [GitHub Copilot 服务](https://github.com/github-copilot/signup)

1. 熟悉 [这个带有 Codespaces 的存储库](https://github.com/github/dotnet-codespaces)

## 💪🏽 练习

**右击以下 Codespaces 按钮在新标签页中打开您的 Codespace**

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/github/dotnet-codespaces)

"**GitHub Codespaces ♥️ .NET 8**" 存储库使用最小 API 构建了一个天气 API，打开了 Swagger 以便您可以调用和测试 API，并使用 .NET 8 在 Web 应用程序中显示数据。

我们将回顾通过添加一个请求特定位置并返回该位置天气预报的新端点来更新天气后端应用程序的步骤。

### 🗒️ (可选步骤 1) : 熟悉 "GitHub Codespaces ♥️ .NET 8" 存储库

当您在 Codespaces 中打开存储库时，您将看到一个全功能的 Codespace 浏览器窗口。此存储库的所有内容都包含在此 Codespace 中。例如，在资源管理器面板中，我们可以看到后端和前端项目的主要代码。

![new Codespace with all the repository running](./005OpenRepoInCodeSpaces.png)

为了运行后端项目，请转到“运行和调试”面板，并选择“后端”项目。

![open program.cs in the BackEnd project](./006RunBackEndProject.png)

开始调试选定的项目。天气 API 项目（我们的后端项目）现在将运行在端口 8080。我们可以从*端口*面板中复制发布的 url

![Copy app url from the ports panel](./007ProjectRunningOpenInNewTab.png)

后端应用程序发布了一个名为`weatherforecast`的端点，该端点生成随机的预报数据。要测试当前运行的应用程序，您可以将`/weatherforecast`添加到发布的 url。最终的 url 应类似于以下内容:

```bash
https://< your url>.app.github.dev/weatherforecast
```
在浏览器中运行的应用程序应类似于此。

![test the running application.](./008TestRunningApi.png)

现在让我们在应用程序中添加一个断点，以调试对 API 的每个调用。转到后端项目中的`Program.cs`文件。该文件位于`SampleApp\BackEnd\Program.cs`路径下。

在第 24 行添加一个断点（按 F9），并使用 URL 刷新浏览器以测试端点。浏览器不应显示天气预报，并且在 Visual Studio 编辑器中我们可以看到程序执行在第 24 行暂停了。

![debug the running application.](./009DebugBackEndDemo.png)

按下 F10，我们可以逐步调试直到第 32 行，在那里我们可以看到生成的值。应用程序应已经生成了未来 5 天的样本天气值。变量`forecast`包含这些值的数组。

![debug the running application.](./010DebugForecastValue.png)

您现在可以停止调试了。

恭喜你！现在您准备好使用 GitHub Copilot 向应用程序添加更多功能了。

### 🗒️ (可选步骤 2) : 熟悉 GitHub Copilot Slash Commands

当我们开始在代码库中工作时，通常需要重构一些代码，或者获取更多上下文或解释。使用 GitHub Copilot 聊天，我们可以进行 AI 驱动的对话来执行这些任务。

打开后端项目中的`Program.cs`文件。该文件位于 `SampleApp\BackEnd\Program.cs`路径下。

现在让我们使用斜杠命令，在 GitHub Copilot 中理解一段代码。选择第 22-35 行，按`CTRL + I`打开内联聊天，并输入`/explain`。

![Use slash command to explain a piece of code](./011SlashCommandExplain.gif)

在聊天面板中，GitHub Copilot 将创建所选代码的详细说明。简化版如下：

```
所选的 C# 代码是使用最小 API 功能的 ASP.NET Core 应用程序的一部分。它在 "/weatherforecast" 处定义了一个 GET 端点，该端点生成一组 WeatherForecast 对象。每个对象都包含一个日期、一个随机温度和一个随机摘要。该端点命名为“GetWeatherForecast”，并具有标准化 API 结构文档的 OpenAPI 支持。
```

**斜杠命令**是您可以在聊天中使用的特殊命令，用于对代码执行特定操作。例如，您可以使用：
- `/doc` 添加文档注释
- `/explain` 解释代码
- `/fix` 为所选代码中的问题提出修复方案
- `/generate` 生成回答您问题的代码

让我们使用 `/tests` 命令为代码生成测试。选择第 39-42 行，按 `CTRL + I` 打开内联聊天，并输入 `/tests` （或选择 /tests 斜杠命令）以生成此记录的一组新测试。

![Use slash command to generate tests for the selected piece of code](./012SlashCmdTests.gif)

此时，GitHub Copilot 将建议一个新类。您需要先按 [Create] 创建新文件。

一个名为`ProgramTests.cs`的新类已创建并添加到项目中。这些测试使用 XUnit，不过，您可以通过类似这样的命令请求生成使用另一个单元测试库的测试：`/tests use MSTests for unit testing`。

***重要**: 我们在此项目中不会使用测试文件。继续之前必须删除生成的测试文件。*

最后，让我们使用 `/doc` 自动生成代码文档。选择第 39-42 行，按 `CTRL + I` 打开内联聊天，并输入 `/doc` （或选择命令）以生成此记录的文档。

![Use slash command to generate the documentation for a piece of code](./013SlashCmdDoc.gif)

内联聊天、聊天面板和斜杠命令是支持 GitHub Copilot 开发体验的绝佳工具。现在我们准备向此应用程序添加新功能。

### 🗒️ 步骤 1: 生成一个包含城市名称的新记录

转到后端项目中的`Program.cs`文件。该文件位于 `SampleApp\BackEnd\Program.cs`。
![open program.cs in the BackEnd project](./011OpenBackEndProject.png)

导航到文件末尾，并请求 Copilot 生成一个包含城市名称的新记录。

```csharp
// 创建一个新的内部记录 WeatherForecastByCity，请求以下参数：City, Date, TemperatureC, Summary
```

生成的代码应类似于下列代码：

```csharp
// 创建一个新的内部记录 WeatherForecastByCity，请求以下参数：City, Date, TemperatureC, Summary
internal record WeatherForecastByCity(string City, DateOnly Date, int TemperatureC, string? Summary)
{
    public int TemperatureF => 32 + (int)(TemperatureC / 0.5556);
}
```

您可以在以下动画中查看提示工作情况：

![open program.cs in the BackEnd project](./014AddNewRecord.gif)

### 🔎 步骤 2: 生成一个新端点以获取某个城市的天气预报

现在，我们来生成一个类似 `/weatherforecast` 但包含城市名称的新 API 端点。新 API 端点名称将为 **`/weatherforecastbycity`**。

***重要**: 您必须在'.WithOpenApi();' 行之后放置代码，这在第 36 行开始。此外，记得在每一行新建议代码出现时都按 TAB 直到整个端点被定义。*

接下来，通过添加如下注释来使用 GitHub Copilot 生成一个新端点：

```csharp
// 创建一个名为 /WeatherForecastByCity/{city} 的新端点，该端点接受 URL 中的城市名称作为参数，并为该城市生成随机预报
```
在以下示例中，我们在之前的端点之后添加了一些额外的空白行，然后 GitHub Copilot 生成了新端点。当端点核心代码生成后，GitHub Copilot 还会建议生成端点名称（第 49 行）和 OpenAPI 规范（第 50 行）的代码。记得按 [TAB] 接受每个建议。

![Copilot ghost suggestion for the new endpoint](./020GeneratedCode.gif)

***重要**: 此提示生成了几行 C# 代码。强烈建议检查和审核生成的代码以确保其按预期工作。*

生成的代码应类似以下内容：

```csharp
// 创建一个名为 /WeatherForecastByCity/{city} 的新端点，该端点接受 URL 中的城市名称作为参数，并为该城市生成随机预报
app.MapGet("/WeatherForecastByCity/{city}", (string city) =>
{
    var forecast = new WeatherForecastByCity
    (
        city,
        DateOnly.FromDateTime(DateTime.Now),
        Random.Shared.Next(-20, 55),
        summaries[Random.Shared.Next(summaries.Length)]
    );
    return forecast;
})
.WithName("GetWeatherForecastByCity")
.WithOpenApi();
```

### 🐍 步骤 3: 测试新端点

最后，通过从“运行和调试”面板启动项目来验证新端点是否工作。选择“运行和调试”，然后选择后端项目。

![Open Run and Debug panel and select BackEnd project](./030RunAndDebugTheBackEndProject.png)

现在按下运行，项目应编译并运行。一旦项目启动，我们可以使用您的 Codespace URL 和原始端点测试原始 Url：

```bash
https://< your code space url >.app.github.dev/WeatherForecast
```

新的端点也将准备就绪以进行测试。以下是一些包含不同城市的示例 URL：
```bash
https://< your code space url >.app.github.dev/WeatherForecastByCity/Toronto

https://< your code space url >.app.github.dev/WeatherForecastByCity/Madrid

https://< your code space url >.app.github.dev/WeatherForecastByCity/<AnyCityName>
```

两个测试运行应如下所示：

![Open Run and Debug panel and select BackEnd project](./032TestAndDebugUsingUrls.png)

🚀 恭喜，通过练习，您不仅使用 GitHub Copilot 生成了代码，还以互动和有趣的方式完成了此任务！您可以使用 GitHub Copilot 不仅生成代码，还可以编写文档、测试应用程序等等。

## 法律声明

Microsoft 和任何贡献者授予您在此存储库中使用 Microsoft 文档和其他内容的许可，
根据 [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode) 
参见 [LICENSE](LICENSE) 文件，并授予您在存储库中使用任何代码的许可，根据 [MIT License](https://opensource.org/licenses/MIT)，
参见 [LICENSE-CODE](LICENSE-CODE) 文件。

文档中提到的 Microsoft、Windows、Microsoft Azure 和/或其他 Microsoft 产品和服务可能是 Microsoft 在美国和/或其他国家的商标或注册商标。
本项目的许可不授予您使用任何 Microsoft 名称、徽标或商标的权利。Microsoft 的一般商标指南可以在 http://go.microsoft.com/fwlink/?LinkID=254653.

隐私信息可以在 https://privacy.microsoft.com/en-us/ 找到。

Microsoft 及任何贡献者保留所有其他权利，无论是根据其各自的版权、专利还是商标，无论是通过暗示、禁止反言或其他方式。