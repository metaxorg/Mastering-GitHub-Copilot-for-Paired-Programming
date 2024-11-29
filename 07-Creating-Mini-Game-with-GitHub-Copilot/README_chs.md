<header>

# 使用 GitHub Copilot 创建一个小游戏

在本模块中，我们将利用 GitHub Copilot 的强大功能来创建一个经典的石头、剪刀、布小游戏。这次实践不仅会提升你的编程技能，还将增强你开发 Python 控制台应用程序的能力。最棒的是？我们将利用 GitHub Codespaces，省去配置开发环境的麻烦。与 GitHub Copilot 作为你的 AI 编程助手，你可以专注于应用开发，并无缝地与代码助手协作。

</header>


- **适合人群**: 开发人员、DevOps 工程师、软件开发经理、测试人员。
- **你将学习到**: 利用 GitHub Copilot 生成代码并为你的工作添加注释。
- **你将构建**: 通过 Copilot AI 生成代码和注释建议的 Python 文件。
- **先决条件**: 要使用 GitHub Copilot，你必须有一个有效的 GitHub Copilot 订阅。注册可免费试用 30 天 [Copilot](https://github.com/settings/copilot)。
- **时间安排**: 本课程可以在一小时内完成。

在本模块结束时，你将获得以下技能：

- 体验 GitHub Codespaces 作为开发环境。
- 开发 Python 控制台应用程序中的输入和输出例程。
- 使用 GitHub Copilot 作为助手。

## 预读内容:
- [使用 GitHub Copilot 入门 prompt 工程](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot//?WT.mc_id=academic-113596-abartolo)
- [挑战项目 - 使用 GitHub Copilot 和 Python 构建一个小游戏](https://learn.microsoft.com/training/modules/challenge-project-create-mini-game-with-copilot/?WT.mc_id=academic-113596-abartolo)
- Learn Live: 使用 GitHub Copilot 构建一个小游戏控制台应用程序（以下视频）
- [![Learn Live: 使用 GitHub Copilot 构建一个小游戏控制台应用程序](https://mediusimg.event.microsoft.com/video-53275/b508053c0b/thumbnail.jpg?sv=2018-03-28&sr=c&sig=k6NthrPwnvBfDPNAEBQaYaVzlJavZ8pnWuP6OcKm4Bs%3D&se=2028-11-18T05%3A23%3A52Z&sp=r)](https://ignite.microsoft.com/sessions/aeaf1e85-65e2-497d-aaf5-724d85213aa1?WT.mc_id=academic-113596-abartolo)
  

## 要求

- 启用你的 [GitHub Copilot 服务](https://github.com/github-copilot/signup)

## 💪🏽 练习

**右键点击“开始课程”按钮，在新标签中打开你的 Codespace**
 
[![start-course](https://user-images.githubusercontent.com/1221423/235727646-4a590299-ffe5-480d-8cd5-8194ea184546.svg)](https://github.com/new?template_owner=skills&template_name=copilot-codespaces-vscode&owner=%40me&name=skills-copilot-codespaces-vscode&description=My+clone+repository&visibility=public)

你已经了解了一些关于 GitHub Codespaces 和 GitHub Copilot 的工作方式。在这个挑战练习中，你的目标是使用 GitHub Copilot 开发一个 Python 小游戏。

#### 测试你的 GitHub Codespace

1. 访问你的 Codespaces，并在 Visual Studio Code 中创建一个名为 *app.py* 的新文件。

   **注意:** 如果尚未安装，你可能需要在 Visual Studio Code 中安装 Python 扩展。

2. 输入以下注释：

   ```python
   # 向控制台输出 'hello world'
   ```
      
3. GitHub Copilot 应该会为你完成代码并提供以下结果：

   ```python
   # 向控制台输出 'hello world'
   print('hello world')
   ```

4. 在终端运行 *python app.py* 命令，并检查结果是否与以下控制台消息相似：

   ```bash
   hello world
   ```
   
### 创建游戏逻辑

既然你已经验证了 Codespaces 与 GitHub Copilot 的配合，那么下一步就是在 GitHub Copilot 的帮助下，根据以下规格开发 Python 小游戏的逻辑：

游戏的胜利由三个简单规则决定：

- **石头** 胜 剪刀。
- **剪刀** 胜 布。
- **布** 胜 石头。

#### 游戏互动考虑

电脑将作为你的对手，随机选择一个元素（**石头**、**剪刀** 或 **布**）。你的游戏互动将通过控制台（终端）进行。

- 玩家可以选择三个选项之一：石头、剪刀或布，并且如果输入了无效选项，则应发出警告。
- 每回合，玩家必须输入列表中的一个选项，并被告知他们是赢了、输了还是与对手平局。
- 每回合结束时，玩家可以选择是否再次游戏。
- 显示玩家在游戏结束时的得分。
- 游戏必须处理用户输入，将其转换为小写字母，并告知用户是否输入了无效选项。

在你的 GitHub Codespaces 中，按照给定的说明设置提示，以帮助 GitHub Copilot 理解并帮助你构建小游戏。请记住，GitHub Copilot 依赖注释来把握上下文，并在你编写项目时为你提供有用的建议。

#### 验证你的工作

1. 在控制台上使用 *python app.py* 命令运行小游戏。
2. 在提示符处输入游戏选项之一：*rock*、*paper* 或 *scissors*。
3. 游戏应该告知玩家是否赢了、输了还是与对手平局。
4. 选择继续游戏。
5. 在提示符输入 *screen*。
6. 游戏应告知玩家输入的选项是否无效。
7. 重复步骤 2 和 4 进行几轮游戏，并选择不继续玩。
8. 检查游戏是否终止，并是否显示你的得分，告知你赢得的次数和总回合数。

恭喜你完成了这个挑战练习！你已经使用 GitHub Copilot 创建了一个 Python 控制台小游戏。