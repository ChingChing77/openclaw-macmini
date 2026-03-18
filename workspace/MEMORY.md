# MEMORY.md - 长期记忆

_只在大会话（飞书私聊）中加载。_

---

## 我是谁

- 名字：**黑莓** 🫐
- 定位：专业助手，专注股票分析、数据整理、任务自动化
- 风格：务实、直接、简洁
- 使命：让大力少操心，多赚钱（或者至少少走弯路）

---

## 关于大力

- 用户名：大力
- 时区：Asia/Shanghai (UTC+8)
- 沟通：飞书（飞书 ID：`ou_f9a2ea548b1320584c1290bdee808c4e`）
- 投资偏好：A股短线交易，6只自选股 + 关注BTC走势
- 偏好：详细技术分析 + 清晰判断理由，简体中文回复

**6只自选股**：赣锋锂业(002460)、祥鑫科技(002965)、瑞泰新材(301238)、中韩半导体ETF(513310)、剑桥科技(603083)、豪威集团(603501)

---

## 重要规则

- 发外部消息（邮件/社交/交易）前必须确认
- 不发不完整的回复
- 投资建议必须标注风险提示
- 群聊：不说大力的私事，不替他表态

---

## 决策记录

### 2026-03-18：网络架构确定
- Mac mini 走 ClashX 代理（7890/7891），akshare/yfinance/Binance 全部通过代理
- 数据源方案：akshare（A股/港股）、yfinance（美股）、Binance API（加密）
- 技能全家桶安装完成，备份系统上线

### 2026-03-19：WiFi 配置完成
- Mac mini WiFi 已连接 CHINESE KITCHEN 5/F（192.168.0.23）
- 主要备用网络：Chou_5G
- 代理环境变量：`http_proxy=http://127.0.0.1:7890`

---

## 教训与陷阱

- **akshare 东方财富域名被封**：需设 `push2delay.eastmoney.com` 或改用新浪接口
- **ClashX 必须常驻**：Mac mini 网络完全依赖代理，断开则定时任务全部失效
- **WiFi networksetup bug**：命令行显示 "not associated" 但实际连接正常，以 ifconfig IP 为准
- **BTC 急跌规律**：UTC 11:00-12:00（北京时间19-20点）容易出现合约清算瀑布

---

## 已安装技能

| 技能 | 用途 |
|------|------|
| stock-analyzer | A股技术分析、K线图 |
| akshare-stock | 量化选股、板块、资金流 |
| china-stock-analysis | A股基本面、估值 |
| stock-watcher | 同花顺自选股监控 |
| us-stock-analysis | 美股技术分析 |
| trading-research | BTC/加密技术分析 |
| binance-pro | Binance 交易 |
| crypto-gold-monitor | 贵金属价格 |
| akshare-finance | 宏观数据（GDP/CPI/PMI/M2） |
| daily-news | 每日新闻聚合 |
| memory-lancedb-pro | 向量记忆检索 |

---

## API Keys

- **Alpha Vantage**：`RO0FRWDTGYKYWHF6`
- **Finnhub**：`d6l547hr01qptf3os23gd6l547hr01qptf3os240`
- **Jina**：已配置

---

## 定时任务

| 任务 | 时间 |
|------|------|
| BTC 预测/验证 | 每小时 0/55 分 |
| A股早/午盘 | 工作日 09:00 / 15:00 |
| 美股报告 | 每天 16:00 |
| 备份 | 每天 22:00 |
| Workspace 精简 | 每周一 08:30 |

---

## 待处理

- [ ] 富途牛牛港股（需安装 FutuOpenD 客户端）
- [ ] TradingView 截图接入（无免费 API）
- [ ] tushare Token 配置（期货/套利数据）
- [ ] Binance API Key 配置（实盘交易）
