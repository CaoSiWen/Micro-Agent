# Micro-Agent 智能体框架

本项目是一个灵活、可扩展的智能体框架，旨在为上层应用提供智能代理能力。Micro-Agent中的"Micro"意为"微"，与微服务中的"微"同义，代表其轻量级、模块化的特性。该框架可用于构建各种智能应用，目前已实现的示例包括代码分析、微服务封装及远程部署等功能。

## 框架特性

Micro-Agent框架的核心特性包括：

1. **灵活的智能体架构**：
   - 支持自定义智能体
   - 提供继承体系便于扩展
   - 灵活的工具调用机制

2. **强大的工具系统**：
   - Python执行工具
   - 命令行工具
   - 文件操作工具
   - 远程连接工具
   - 支持自定义工具开发

3. **基于大语言模型的推理能力**：
   - 支持OpenAI等LLM接口
   - 可扩展的LLM适配器

4. **完整的开发文档**：
   - 详细的架构说明
   - 工具开发指南
   - 示例代码

## 已实现的示例应用

目前，框架已实现以下示例应用：

1. **代码分析 Agent**：
   - 自动分析代码结构和依赖关系
   - 生成代码依赖可视化图表
   - 输出详细的代码分析报告

2. **服务封装 Agent**：
   - 将现有代码自动封装为微服务
   - 生成Docker配置文件
   - 创建微服务部署所需的全部资源

3. **远程部署 Agent**：
   - 将封装好的微服务自动部署到远程服务器
   - 提供部署状态监控
   - 支持部署过程的日志记录和查看

## 系统架构

Micro-Agent框架的主要组件包括：

- 智能体系统（BaseAgent, ReActAgent, ToolCallAgent等）
- 工具系统（BaseTool及各种具体工具实现）
- 提示系统
- 语言模型接口
- 配置系统

## 开发与使用

### 开发环境设置

- 建议python版本为3.12.

1. 克隆仓库：
   ```bash
   git clone https://github.com/PolarSnowLeopard/Micro-Agent
   cd Micro-Agent
   ```

2. 使用conda创建python环境（可选）：
   ```bash
   conda create -n micro-agent python=3.12
   conda activate micro-agent
   ```

3. 创建并配置环境变量文件：
   ```bash
   cp .env.example .env
   cp config/config.example.toml config/config.toml
   # 编辑.env和config/config.toml文件，设置所需的API密钥和配置参数
   ```

4. 安装依赖：
   ```bash
   pip install -r requirements.txt
   ```

### 文档中心

项目提供了完整的文档中心，可通过以下方式访问(或访问线上文档[fdueblab.cn/docs](https://fdueblab.cn/docs))：

1. 启动文档服务器：
   ```bash
   cd docs
   python -m http.server 8000
   ```

2. 浏览器访问：`http://localhost:8000`

文档中心包含详细的系统架构说明、API文档、智能体开发指南以及工具开发指南。有关自定义开发、创建自定义智能体和工具的具体方法，请参考文档中心的相关章节。

## 配置选项

Micro-Agent框架使用两个主要的配置文件：

1. **`.env`文件**：用于存储环境变量和敏感信息
   - 从`.env.example`复制得到：`cp .env.example .env`
   - 包含的主要配置：
     - `REMOTE_SSH_SERVER`: 远程服务器地址
     - `REMOTE_SSH_USERNAME`: 远程服务器用户名
     - `REMOTE_SSH_PASSWORD`: 远程服务器密码

2. **`config/config.toml`文件**：用于系统主要配置
   - 从`config/config.example.toml`复制得到：`cp config/config.example.toml config/config.toml`
   - 包含的主要配置：
     - LLM模型配置（API密钥、模型名称、参数等）
     - 视觉模型配置
     - 代理配置（可选）

在使用系统前，请确保这两个配置文件都已正确设置。特别是需要添加您的LLM API密钥以及其他必要的连接信息。

## 日志和调试

系统日志存储在`logs/`目录下，可用于故障排查和系统监控。