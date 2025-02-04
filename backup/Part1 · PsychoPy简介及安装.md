# 一、关于PsychoPy
PsychoPy 是一款功能强大的开源软件，专门用于心理学、神经科学和相关领域的研究。它由英国诺丁汉大学的 Jonathan Peirce 教授团队从开发，旨在为研究者提供一个灵活、免费、易用且功能强大的平台，用于创建和控制各种类型的实验任务。

PsychoPy 迄今已更新超过20年，在经历过一百多个版本的迭代后，在全世界各高校和研究机构中有众多用户。

在本教程中，将基于2024年最新发布的 ***2024.2.4*** 版本进行讲解。

## （一）PsychoPy 的优势与特点

- **开源免费**：PsychoPy 完全开源且免费，大大降低了科研成本。且PsychoPy 使用GPL-3.0协议，任何用户都可以自由使用、修改和分发，也能很方便的找到源码，便于深入学习了解其后的详细设计。
- **跨平台**：PsychoPy 跨平台支持 Windows、macOS 和 Linux 操作系统，方便研究人员在不同的平台上进行实验设计和运行。
- **易于使用**：PsychoPy 提供了图形化界面（Builder 视图）和代码界面（Coder 视图）两种操作方式。即使没有编程经验的用户也可以通过 Builder 视图快速创建简单的实验。对于需要更高级定制的实验，可以使用 Coder 视图编写 Python 代码。
- **精确的时序控制**：PsychoPy 能够提供精确到毫秒级别的时间控制，这对于需要精确测量反应时和刺激呈现时间的心理学实验至关重要。
- **丰富、灵活的刺激呈现功能**：PsychoPy 支持呈现各种类型的刺激，包括图像、文本、声音和视频等。它还支持使用 OpenGL 进行高级图形渲染，可以创建复杂的视觉刺激。
- **与其他 Python 库的良好兼容性**：PsychoPy 可以与 NumPy、Matplotlib、Pandas 和 SciPy 等其他常用的 Python 科学计算库无缝集成，方便进行数据分析和处理。
- **可扩展性**：PsychoPy可以兼容一系列研究硬件，如EEG、fMRI、眼动仪、反应盒、麦克风、多个显示器等
- **在线和离线实验**：使用 PsychoPy 既可以创建传统的实验室实验，也能方便地生成在线实验，在在线实验平台上运行，以满足不同的研究需求。
- **丰富的学习材料和活跃的社区支持**：Jonathan Peirce 教授团队目前已撰写了两版教材《Building Experiments in PsychoPy》，在[官网](https://www.psychopy.org/PsychoPyManual.pdf)也有详细的说明文档，以及一个活跃的[用户社区](https://discourse.psychopy.org/)，方便使用者寻求帮助和分享经验。

## （二）如何获取 PsychoPy
通常情况下，可以从 PsychoPy 的[官方网站](https://psychopy.org/)上Download标签页下载到最新版本的 PsychoPy ，也可以从 PsychoPy项目的[GitHub仓库](https://github.com/psychopy/psychopy/releases)中找到特定版本的PsychoPy 下载。

有时候可能从官网下载会出现下载慢或者连接失败的情况，如果无法从官网顺利下载，本教程配套的线上资源中也为大家准备了一些常用版本的PsychoPy ，方便下载使用。

# 二、PsychoPy的安装

PsychoPy 的安装相对简单，但根据你的操作系统和 Python 环境，可能需要选择不同的安装方法。

###  1.通过独立安装包
对于大多数用户来说，推荐使用 PsychoPy 官方提供的独立安装包。这种方式最为简单快捷，无需配置 Python 环境，适合初学者。

独立安装包中打包好了一整套Python 环境，以及支持PsychoPy 各项功能的Python 库，开箱即用，并且会在应用列表里直接添加PsychoPy，因此安装好之后可以像运行一个独立软件一样，点击即打开PsychoPy 的界面。

如果不需要考虑运行旧版本的PsychoPy 实验程序，可以在官网的[Download页面](https://www.psychopy.org/download.html)上下载你使用的操作系统（Windows、MacOS或Linux）所对应的modern 独立安装包（使用的Python版本为3.10.11）。

双击下载的安装包，按照提示步骤进行安装。

在 Windows 系统上，你可能需要以管理员身份运行安装程序。安装完成后，即可以在开始菜单（Windows）或应用程序文件夹（macOS）中找到 PsychoPy 的图标。

###  2.通过pip安装
由于PsychoPy 本质是一个基于Python 编写的库，所以可以在先在电脑上安装Python 环境之后，通过*pip install*的方式来安装。

通常来说，建议电脑上已安装的Python 版本为3.10或3.8，使用其它的版本有可能会遇到不能正常安装或运行的问题。

已经准备好合适的Python 环境后，可以通过以下语句来安装最新版的PsychoPy ：

```bash
pip install psychopy
```

如果需要安装特定版本的PsychoPy ，可以通过以下语句来指定版本：

```bash
pip install psychopy==2024.2.4
```

安装特定版本的前提是输入的版本号是正确的，可以在GitHub 上查找你想要的[具体版本](https://github.com/psychopy/psychopy/releases)。
	
> [!TIP]
> 考虑到PsychoPy 所依赖的众多Python 库有可能与你已在其它项目中使用的某些库存在版本冲突的情况（例如，项目 A 需要使用numpy的 1.19 版本，而项目 B 需要使用numpy的 1.21 版本），建议通过Conda(Anaconda) / virtualenv / venv甚至pyenv等工具创建虚拟环境，再在这个虚拟环境中单独配置PsychoPy ，这样能更好的完成环境的隔离与保护。

###  3.其它安装方式
在Linux 上也需要通过先配置Python 环境再*pip install*的方式安装PsychoPy ，而在MacOS上，还可以通过*brew install*的方式安装PsychoPy。

这些安装方式在官网上有[更加详细的说明](https://www.psychopy.org/download.html)，可以参考。