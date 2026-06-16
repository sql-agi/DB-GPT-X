# DB-GPT-X: Using natural language to manage databases, replacing traditional enterprise web management backend interfaces

<p align="center">   <img src="./img/logo.jpg" width="75%" /> </p>

<div align="center">
  <p>
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
  </p>
 👋 Join our <a href="img/WECHAT.md" target="_blank">WeChat</a>
</div>


## Introduction

🤖  DB-GPT-X is an open-source data application development framework aimed at utilizing Large Language Model (LLM) technology to interact with databases through natural language, replacing traditional web management backend. 

🌐  At present, we only have access to query permissions. In order to meet more complex business requirements, including the Create, Read, Update, and Delete (CRUD) functionality, we are currently undergoing internal testing and we look forward to bringing more surprises to everyone in the future.

🚀  In the era of Data 3.0, our products are committed to utilizing model and database technologies to enable enterprises and developers to build custom applications with less code. Enable developers to focus more on complex C-end business and replace traditional web management backend systems.

## Quick Start
Find a directory where the project is stored and clone it. The cloning command is as follows:
```shell
git clone https://github.com/sql-agi/DB-GPT-X
```
### Docker deploy
Firstly, configure the .env file, which can refer to templates .env_temple;

You only need to configure the OPENAI_API_KEY and OPENAI_API_BASE attributes (it is recommended to use the official API_KEY);

Then switch to the Docker directory and refer to README.md in the Docker directory. The switching command is as follows:

```shell
cd DB-GPT-X/docker
```
Finally, execute the command README.md;

Note: If you need to customize the database table structure and table data, simply change the /docker/sql/init.sql file in the root directory

### Web & CLI

Firstly, create a new environment using Conda and switch the environment to db-gpt. The command is as follows:

```shell
conda create --name db-gpt python=3.9
conda activate db-gpt
pip install -r requirements.txt
```

Configure the .env file, you can refer to templates .env_temple

The main configuration includes these attributes: OPENAI_API_KEY、OPENAI_API_BASE、MYSQL_HOST、MYSQL_PORT、MYSQL_USER、MYSQL_PASSWORD、MYSQL_DATABASE

🔥🔥🔥 I strongly recommend that everyone use the official API_KEY. After testing, some intermediate keys do not support good results

#### web demo

We provide a method based on [Gradio](https://gradio.app) web version demo and a command-line demo:

![web-demo](img/web.jpg)

Then run [web_demo.py](web_demo.py) in the repository:

```shell
python web_demo.py
```

The program will run a web server and output the address. Open the output address in the browser to use it. The latest version of the demo has achieved a typewriter effect, greatly improving the speed experience. Note that due to slow network access in domestic Gradio, when 'demo. queue(). launch (share=True, inbrowser=True)' is enabled, all networks will be forwarded through the Gradio server, resulting in a significant decrease in the typewriter experience. The default startup method has now been changed to 'share=False'. If there is a need for public network access, it can be changed to 'share=True' startup.

#### cli demo
![cli-demo](img/cli_01.jpg)

![cli-demo](img/cli_02.jpg)

Run [cli_demo.py](cli_demo.py) in the repository:

```shell
python cli_demo.py
```

The program will have an interactive conversation on the command line. Enter instructions and press enter on the command line to generate a reply, and enter 'quit' to terminate the program.

### API Deploy

Run [api.py](api.py) in the repository:

```shell
python api.py
```
Deployed locally on port 8000 by default, called through POST method

```shell
curl -X POST "http://127.0.0.1:8000/chat/db" \
     -H "Content-Type: application/json" \
     -d '{"input": "你好"}'
```
The obtained return value is

```shell
{
    "reply": "你好！请问有什么可以帮助您的？"
}
```

## Future Plans
🔥🔥🔥 Front end UI interface: We are committed to developing better front-end UI interfaces, further supporting a wider range of databases and LLMs (including open-source big models), to enhance user experience and system flexibility.

🔥🔥🔥 Backend: We will further conduct in-depth testing on more complex CRUD scenarios, adding functions such as distinguishing (switching) environments and setting role permissions to ensure the accuracy and stability of LLM operations.

🔥🔥🔥 Summary: We hope to provide more user experience and feedback, and we will further optimize our products based on user feedback. We also hope that interested partners can join our open source team.

## Contact Us

### Project communication group

<img src="img/qr_code_wechat.jpg" alt="二维码" width="300" />

🎉 Chat_DB Project WeChat communication group. If you are also interested in this project, please join the group chat to participate in discussions and exchanges.

### Official Account

<img src="img/qr_code_account.jpg" alt="二维码" width="300" />

🎉 Chat_DB official account, welcome to scan the code.

## 🤗 Reference project
https://github.com/langchain-ai/langchain
