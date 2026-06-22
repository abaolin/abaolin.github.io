---
title: 用 LLM 打造零成本的多市场股票智能分析系统
date: 2026-06-22 19:24:29 +0800
categories: [Tech, Backend]
tags: [Backend, Tech, LLM, GitHub Actions, Stock Analysis, Automation, Python, Webhook]
image:
  path: /assets/img/posts/2026-06-22-llm-powered-multi-market-stock-analysis/cover.jpg
  alt: 用 LLM 打造零成本的多市场股票智能分析系统
---

## 核心内容提炼

一套基于大模型的 A股/港股/美股/日股/韩股自选股智能分析系统，整合多源行情与实时新闻，每日自动生成决策仪表盘并推送到企业微信、飞书、Telegram 等渠道，可借助 GitHub Actions 实现零成本定时运行，也支持本地与 Docker 部署。

> 由 claude-opus-4-8 模型总结提炼，观点仅供参考。

## 项目概览

这是一个 LLM 驱动的多市场股票智能分析系统，核心目标是把繁琐的盯盘、信息搜集和研判工作交给自动化流程。系统覆盖 A股、港股、美股、日股和韩股的自选股，每个交易日自动运行分析，并以「决策仪表盘」的形式推送结论。

主要能力包括：

- **多源行情数据**：聚合多个数据源，按优先级降级保证可用性。
- **实时新闻与舆情**：接入搜索服务，抓取公告、事件和催化因素。
- **大模型研判**：用 LLM 综合行情、技术指标和新闻给出评分与买卖观望建议。
- **多渠道推送**：支持企业微信、飞书、Telegram、Discord、Slack、邮箱。
- **零成本运行**：依托 GitHub Actions 定时触发，无需自建服务器。

技术栈以 Python 为主（约 75%），Web 工作台由 TypeScript 构建。

## 方式一：基于 GitHub Actions 的零成本部署

对于不想维护服务器的用户，GitHub Actions 是推荐路径，大约 5 分钟即可完成部署。

核心步骤：

1. **Fork 仓库**：点击右上角 Fork（顺手 Star 支持作者）。
2. **配置 Secrets**：在 `Settings → Secrets and variables → Actions → New repository secret` 中添加密钥。
3. **配置 AI 模型**（至少一个）：选定一个模型服务商并填入 API Key，云端 API 更适合 Actions 环境；本地或 Docker 部署可考虑 Ollama。
4. **配置通知渠道**（至少一个）：根据需要接入企业微信、飞书或邮箱等。
5. **配置自选股**（必填）：填写要跟踪的股票代码。
6. **配置新闻源**（推荐）：新闻源直接影响舆情、公告和催化因素的质量，建议至少配置一个搜索服务。
7. **启用并运行**：在 Actions 标签确认启用工作流，可手动 `Run workflow` 触发。

默认行为是**每个工作日北京时间 18:00** 自动执行，且自动跳过 A/H/US 的非交易日，避免无效运行。

## 方式二：本地运行与 Docker 部署

如果希望完全自主掌控环境，可以直接在本地或 Docker 中运行。

```bash
# 克隆项目
git clone https://github.com/ZhuLinsen/daily_stock_analysis.git && cd daily_stock_analysis
# 安装依赖
pip install -r requirements.txt
# 配置环境变量
cp .env.example .env && vim .env
# 运行分析
python main.py
```

常用命令示例：

```bash
python main.py --debug                          # 调试模式
python main.py --dry-run                         # 试运行，不实际推送
python main.py --stocks 600519,hk00700,AAPL     # 指定股票分析
python main.py --market-review                   # 大盘复盘
python main.py --schedule                        # 启动定时任务
python main.py --serve-only                       # 仅启动服务
```

Docker 部署、定时任务和云服务器访问可参考项目的完整指南。

## 推送效果：决策仪表盘与大盘复盘

系统的输出以「决策仪表盘」为核心，把每只股票的研判结果浓缩为评分、买卖观望信号和关键信息速览。

仪表盘内容通常包括：

- **结果摘要**：买入/观望/卖出的数量统计与单股评分。
- **舆情情绪**：市场情绪倾向与短期资金压力提示。
- **业绩预期**：基于基本面与舆情对业绩的判断。
- **风险警报**：主力资金流出、筹码集中度、历史违规等风险点。
- **利好催化**：行业定位、业绩增长等正向因素。
- **最新动态**：抓取到的最新消息汇总。

除了个股分析，系统还能生成「大盘复盘」，输出主要指数涨跌、上涨下跌家数、涨跌停统计以及领涨领跌板块，帮助快速把握市场全局。

## Web 工作台与 Agent 策略问股

系统提供完整的 Web 工作台，启动方式：

```bash
python main.py --webui       # 带分析的 WebUI
python main.py --webui-only  # 仅启动 WebUI
```

访问 `http://127.0.0.1:8000` 即可使用，功能涵盖配置管理、任务监控、手动分析、历史报告、Markdown 报告查看、回测、持仓管理、智能导入以及浅色/深色主题。

**Agent 策略问股**是亮点功能：配置任意可用的 AI API Key 后，即可在 `/chat` 页面进行策略问股（设置 `AGENT_MODE=false` 可关闭）。它支持：

- 多种内置策略：均线金叉、缠论、波浪理论、多头趋势、热点题材、事件驱动、成长质量、预期重估等。
- 实时行情、K 线、技术指标、新闻和风险信息的调用。
- 多轮追问、会话导出、发送到通知渠道和后台执行。
- 自定义策略文件与多 Agent 编排（实验性）。

## 配置要点与生态延伸

系统的核心可配置项围绕几个维度展开：环境变量、模型渠道、通知渠道、数据源优先级、交易纪律以及基本面 P0 超时语义。这些细节决定了分析质量与运行稳定性，建议参考项目的完整配置指南逐项设置。

本项目（DSA）聚焦日常分析报告，作者还维护了同系列的选股、策略验证与策略进化项目，三者当前独立维护，未来会优先探索候选股导入、回测验证与报告联动的打通。

项目采用 MIT License 开源。需要特别强调的是：**本系统仅供学习与研究使用，不构成任何投资建议，股市有风险，投资需谨慎。**

## 原文链接

- [阅读原文](https://github.com/ZhuLinsen/daily_stock_analysis/tree/main)
