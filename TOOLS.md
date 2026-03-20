# TOOLS.md - 本地工具速查

> TOOLS.md = 机器可读的快速参考，存放 IP、路径、Key 等硬数据
> MEMORY.md = 人的记忆，存放决策、偏好、教训

---

## 网络

| 项目 | 值 |
|------|-----|
| ClashX HTTP | `127.0.0.1:7890` |
| ClashX SOCKS | `127.0.0.1:7891` |
| WiFi IP | `192.168.0.23` (en1) |
| WiFi SSID | CHINESE KITCHEN 5/F |

**Python 代理**：`os.environ['http_proxy']='http://127.0.0.1:7890'`

---

## 目录

| 目录 | 路径 |
|------|------|
| Workspace | `~/.openclaw/workspace/` |
| Scripts | `~/.openclaw/scripts/` |
| Memory | `~/.openclaw/workspace/memory/` |
| Skills | `~/.openclaw/skills/` |

---

## 数据源（最优方案）

```
A股/港股  → akshare（新浪+东方财富，通过代理）
美股      → yfinance（Yahoo Finance）
加密货币  → Binance API（通过代理）
宏观外汇  → akshare + yfinance
```

**详见**：`MEMORY.md` / `skills/akshare-stock/SKILL.md` / `skills/trading-research/SKILL.md`

---

## API Keys

| 服务 | Key |
|------|-----|
| Alpha Vantage | `RO0FRWDTGYKYWHF6` |
| Finnhub | `d6l547hr01qptf3os23gd6l547hr01qptf3os240` |
| Jina | 已配置 |

---

## 飞书

- 用户 ID：`ou_f9a2ea548b1320584c1290bdee808c4e`

---

## 定时任务（Cron）

| 任务 | 时间 | 说明 |
|------|------|------|
| BTC 预测 | 每小时 0 分 | ⚠️ 需代理畅通 |
| BTC 验证 | 每小时 55 分 | 验证上一轮预测 |
| A股 早盘 | 工作日 09:00 | 市场分析 |
| A股 午盘 | 工作日 15:00 | 收盘总结 |
| 美股报告 | 每天 16:00 | |
| 备份 | 每天 22:00 | → GitHub |
| 精简 | 每周一 08:30 | Workspace 清理 |

---

## 技能速查

```
A股/港股 → akshare-stock + china-stock-analysis + stock-watcher
美股      → us-stock-analysis
加密      → trading-research + binance-pro
宏观      → akshare-stock（板块/资金流）
每日新闻  → daily-news + news-aggregator
办公工具  → excel-xlsx + word-docx + powerpoint-pptx + pdf
```

详见：`MEMORY.md` 已安装技能列表
