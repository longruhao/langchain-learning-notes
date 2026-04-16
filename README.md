# Personal Chief AI (私厨智能助手)

一个基于 FastAPI 和 LangChain 构建的智能私厨助手后端项目。该项目旨在通过 AI 大模型为用户提供个性化的菜谱推荐、食材管理以及多模态交互体验，并集成阿里云 OSS 实现图片的高效存储与访问。

## 🚀 技术栈

- **核心框架**: FastAPI, Uvicorn
- **AI 编排**: LangChain v1.2, LangChain Community, LangChain OpenAI
- **模型支持**: OpenAI, DashScope (通义千问), DeepSeek
- **云存储**: Alibaba Cloud OSS V2
- **包管理**: uv (极速 Python 包安装器)
- **前端交互**: Next.js (位于 `marry-ai` 目录)
- **开发工具**: Jupyter Notebook, Python-dotenv

## 📂 项目结构

```
text
langchain_v1.2/
├── app/                  # FastAPI 后端源码
│   ├── api/v1/           # API 路由 (对话、OSS 签名等)
│   ├── common/           # 通用工具 (日志配置)
│   ├── models/           # 数据模型 (Pydantic Schemas)
│   ├── static/           # 静态资源 (前端打包文件)
│   └── main.py           # 应用入口
├── jupyter/              # 算法实验与学习笔记
│   ├── notebooks/        # LangChain 学习案例
│   └── pyproject.toml    # 笔记环境的依赖配置
├── marry-ai/             # Next.js 前端源码
├── pyproject.toml        # 项目依赖与配置
└── uv.lock               # 依赖锁定文件
```
## 🛠️ 环境准备与运行

本项目使用 `uv` 进行依赖管理，要求 Python 版本 >= 3.13。

### 1. 安装依赖

确保已安装 [uv](https://docs.astral.sh/uv/)，然后在项目根目录执行：

```
bash
# 创建并激活虚拟环境
uv venv
source .venv/bin/activate  # Linux/Mac
# .venv\Scripts\Activate.ps1  # Windows PowerShell

# 同步依赖
uv sync
```
### 2. 配置环境变量

在项目根目录创建 `.env` 文件，填入必要的密钥：

```
env
# OpenAI / DeepSeek / DashScope API Key
OPENAI_API_KEY=your_api_key_here
DASHSCOPE_API_KEY=your_api_key_here

# 阿里云 OSS 配置
ALIBABA_CLOUD_ACCESS_KEY_ID=your_access_key_id
ALIBABA_CLOUD_ACCESS_KEY_SECRET=your_access_key_secret
OSS_BUCKET=your_bucket_name
OSS_ENDPOINT=oss-cn-beijing.aliyuncs.com
```
### 3. 启动服务

```
bash
python -m app.main
```
服务默认运行在 `http://127.0.0.1:8001`。

## 📝 功能特性

- **智能对话**: 基于 LangChain 的多轮对话能力，支持上下文记忆。
- **图片上传**: 集成阿里云 OSS，提供安全的预签名上传接口。
- **前后端分离**: 后端提供 RESTful API，前端采用 Next.js 现代化架构。
- **学习记录**: 包含完整的 LangChain 学习笔记与实战代码（Jupyter Notebooks）。

## 📄 License

This project is licensed under the MIT License.
