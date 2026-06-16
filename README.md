# DB-GPT-X

> 用自然语言管理数据库——替代传统企业 Web 管理后台。

<p align="center">
  <img src="./img/logo.jpg" width="75%" />
</p>

<div align="center">
  <a href="https://github.com/sql-agi/DB-GPT-X">
    <img alt="stars" src="https://img.shields.io/github/stars/sql-agi/DB-GPT-X" />
  </a>
  <a href="https://github.com/sql-agi/DB-GPT-X">
    <img alt="forks" src="https://img.shields.io/github/forks/sql-agi/DB-GPT-X" />
  </a>
  <a href="https://opensource.org/licenses/MIT">
    <img alt="License: MIT" src="https://img.shields.io/github/license/sql-agi/DB-GPT-X" />
  </a>
  <a href="https://github.com/sql-agi/DB-GPT-X/releases">
    <img alt="Release Notes" src="https://img.shields.io/github/v/release/sql-agi/DB-GPT-X" />
  </a>
  <a href="https://github.com/sql-agi/DB-GPT-X/issues">
    <img alt="Open Issues" src="https://img.shields.io/github/issues-raw/sql-agi/DB-GPT-X" />
  </a>
  <br/>
  👋 加入我们的 <a href="img/WECHAT.md" target="_blank">微信群</a>
</div>

---

## 项目声明

DB-GPT-X 是由 sql-agi 团队独立开发和维护的开源项目。

本项目与 eosphoros-ai/DB-GPT 无任何关联、背书、衍生或技术继承关系。

DB-GPT-X 的所有源代码、架构设计和核心实现均由 sql-agi 团队独立自主研发。

---

## 目录

- [项目介绍](#项目介绍)
- [快速上手](#快速上手)
  - [Docker 部署](#docker-deploy)
  - [Web & CLI](#web--cli)
  - [API 部署](#api-deploy)
- [未来计划](#未来计划)
- [联系我们](#联系我们)

---

## 项目介绍

🤖 DB-GPT-X 是一个开源的数据应用程序开发框架，旨在利用大型语言模型（LLM）技术通过自然语言与数据库进行交互，取代传统的 Web 管理后台。

🌐 目前开放查询权限。完整的增删改查（CRUD）功能正在内部测试中，即将推出。

🚀 在 Data 3.0 时代，DB-GPT-X 让企业和开发者用更少的代码构建自定义应用，专注于复杂的业务逻辑，而非维护管理后台。

---

## 快速上手

```shell
git clone https://github.com/sql-agi/DB-GPT-X
```

### Docker Deploy

1. 配置 `.env` 文件（参考 `templates.env_temple`）
2. 填写 `OPENAI_API_KEY` 和 `OPENAI_API_BASE`（建议使用官方 API Key）
3. 切换到 docker 目录：

```shell
cd DB-GPT-X/docker
```

4. 参照 `docker/README.md` 执行对应命令

> **注意：** 如需自定义数据库表结构或初始数据，修改 `/docker/sql/init.sql` 即可。

### Web & CLI

**环境要求：** Python 3.9、Conda

```shell
conda create --name db-gpt python=3.9
conda activate db-gpt
pip install -r requirements.txt
```

配置 `.env` 文件（参考 `templates.env_temple`）：

| 变量 | 是否必填 |
|---|---|
| `OPENAI_API_KEY` | ✅ |
| `OPENAI_API_BASE` | ✅ |
| `MYSQL_HOST` | ✅ |
| `MYSQL_PORT` | ✅ |
| `MYSQL_USER` | ✅ |
| `MYSQL_PASSWORD` | ✅ |
| `MYSQL_DATABASE` | ✅ |

> 🔥 强烈建议使用官方 OpenAI API Key，经测试部分中转 Key 效果不稳定。

#### Web Demo

![web-demo](img/web.jpg)

```shell
python web_demo.py
```

程序启动后输出本地地址，在浏览器中打开即可使用。最新版已实现打字机效果，体验大幅提升。

> 默认 `share=False`。如需公网访问，在 [web_demo.py](web_demo.py) 中改为 `share=True`（注意：通过 Gradio 中转会降低打字机响应速度）。

#### CLI Demo

![cli-demo](img/cli_01.jpg)

![cli-demo](img/cli_02.jpg)

```shell
python cli_demo.py
```

在命令行中进行交互式对话，输入 `quit` 退出。

### API Deploy

```shell
python api.py
```

默认在本地 `8000` 端口启动，通过 POST 方法调用：

```shell
curl -X POST "http://127.0.0.1:8000/chat/db" \
     -H "Content-Type: application/json" \
     -d '{"input": "你好"}'
```

返回值：

```json
{
    "reply": "你好！请问有什么可以帮助您的？"
}
```

---

## 未来计划

- **前端：** 更优秀的 UI 界面，支持更多数据库类型及开源大模型
- **后端：** 深度测试复杂 CRUD 场景，增加环境切换、角色权限管理
- **社区：** 持续根据用户反馈优化产品，欢迎感兴趣的开发者加入开源团队

---

## 联系我们

### 项目交流群

<img src="img/qr_code_wechat.jpg" alt="微信群二维码" width="300" />

欢迎加入 DB-GPT-X 微信交流群，参与讨论与反馈。

### 公众号

<img src="img/qr_code_account.jpg" alt="公众号二维码" width="300" />

欢迎扫码关注官方公众号，获取最新动态。

---

## 参考项目

- [LangChain](https://github.com/langchain-ai/langchain)

---

## 项目声明

DB-GPT-X 是由 sql-agi 团队独立开发的开源项目，与 eosphoros-ai/DB-GPT 无任何关联、背书或衍生关系。
