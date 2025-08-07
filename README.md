# mcp-server-oracle-11g

[![Python 3.10](https://img.shields.io/badge/python-3.10-blue.svg)](https://www.python.org/downloads/release/python-3100/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> 项目最初参考了 mcp-oracle 开源项目：[点这里跳转](https://github.com/anpy-j/mcp-oracle)

## 特性说明

适配 Oracle 11g 低版本，不再需要安装 VS 以及 C++ 编译等一些步骤，但是需要指定 Oracle 客户端变量路径（一般使用 Oracle 或者 PL/SQL 的都有这个 Client-Lib 的路径）

⚠️ *包目前暂未发布到官仓，仅供本地测试使用*

## 模式支持

1. stdio 模式
2. sse 模式

## 前置要求

- UV (包管理器)
- Python 3.10+
- Cherry Studio

## 变量说明

`ORACLE_USER` 数据库用户名：譬如 `system`  
`ORACLE_PASSWORD` 数据库密码：譬如 `password`  
`ORACLE_URL` 数据库连接地址：譬如 `localhost:1521/orcl`  
`ORACLE_HOME` Oracle 客户端路径：譬如 `C:\oracle\instantclient_19_8`

## 使用说明

克隆仓库到本地
```bash
git clone https://github.com/jobslee0/mcp-oracle-11g.git
```

1. stdio 模式

项目包install

```bash
cd mcp-oracle-11g\pkg
pip install -e .
```

配置客户端及变量

模式：`stdio`

命令：`uv`

参数：
```bash
--directory
E:\path\to\local\pkg
run
db_oracle_get_mcp
```

环境变量：
```bash
ORACLE_USER=用户名  
ORACLE_PASSWORD=密码  
ORACLE_URL=数据库路径，譬如127.0.0.1:1521/xxx  
ORACLE_HOME=Oracle客户端路径，譬如path\to\instantclient_xxx
```

2. sse 模式

配置和启动项目

修改 .env 文件
```bash
ORACLE_USER=用户名  
ORACLE_PASSWORD=密码  
ORACLE_URL=数据库路径，譬如127.0.0.1:1521/xxx  
ORACLE_HOME=Oracle客户端路径，譬如path\to\instantclient_xxx  
```

启动 sse 服务
```bash
python run.py
```

配置客户端及变量

模式：`sse`

URL：`http://127.0.0.1:8000/sse`

## 许可证

本项目采用 MIT 许可证 - 详情请查看 [LICENSE](LICENSE) 文件。
