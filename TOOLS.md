# TOOLS.md - 本地工具速查

> 硬数据（IP/路径/Key）存这里；软记忆（决策/教训）存 MEMORY.md

---

## 网络

| 项目 | 值 |
|------|-----|
| ClashX HTTP | `127.0.0.1:7890` |
| ClashX SOCKS | `127.0.0.1:7891` |
| WiFi IP | `192.168.0.23` (en1) |
| WiFi SSID | CHINESE KITCHEN 5/F |

---

## 目录

| 目录 | 路径 |
|------|------|
| Workspace | `~/.openclaw/workspace/` |
| Scripts | `~/.openclaw/scripts/` |
| Backups | `~/.openclaw/backups/` |
| Skills | `~/.openclaw/skills/` |
| ClawTeam | `~/.clawteam/` |

---

## A股数据源（最优方案）

**国内站**（腾讯/akshare）：清除所有代理环境变量后直连

```python
import os
for k in list(os.environ.keys()):
    if 'proxy' in k.lower(): os.environ.pop(k, None)
```

| 数据源 | 接口 | 状态 | 说明 |
|--------|------|------|------|
| 腾讯行情 | `qt.gtimg.cn` | ✅ **主力** | 秒级响应，parts[32]=涨跌幅 |
| akshare | `push2delay.eastmoney.com` | ✅ 可用 | 全量5000只慢，patch后可用 |
| efinance | `hsmarketwg.eastmoney.com` | ⚠️ 不稳定 | 单股查询偶发失败 |

**akshare patch**：akshare 用 `push2.eastmoney.com:443`（被封）→ 批量 patch 到 `push2delay.eastmoney.com:80`

```bash
# patch 脚本（venv 内运行）
AKS=~/.openclaw/workspace/stock-dashboard/backend/venv/lib/python3.14/site-packages/akshare
find $AKS -name "*.py" | xargs sed -i '' \
  -e 's/push2\.eastmoney\.com/push2delay.eastmoney.com/g' \
  -e 's/push2his\.eastmoney\.com/push2delay.eastmoney.com/g' \
  -e 's/[0-9]\+\.push2\.eastmoney\.com/push2delay.eastmoney.com/g'
```

---

## 美股数据源

| 数据源 | 说明 |
|--------|------|
| Alpha Vantage | 免费key每日25次，今天用完会返回0 |
| Yahoo Finance | 直连被限流（HTTP 429） |

---

## 加密数据源

| 数据源 | 说明 |
|--------|------|
| Binance API | 走代理 `http://127.0.0.1:7890`，直连被 reset |

---

## 项目

| 项目 | 路径 |
|------|------|
| 股票看板 | `~/.openclaw/workspace/stock-dashboard/` |
| 启动后端 | `cd backend && source venv/bin/activate && python main.py` |
| 启动前端 | `cd frontend && npm run dev` |
| 数据采集 | `python data/data_pipeline.py` |
| 看板地址 | `http://localhost:5173` |

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

| 任务 | 时间 |
|------|------|
| BTC 预测/验证 | 每小时 0/55 分 |
| A股早/午盘 | 工作日 09:00 / 15:00 |
| 美股报告 | 每天 16:00 |
| 备份 | 每天 22:00 |
| Workspace 精简 | 每周一 08:30 |

---

## 常见错误

| 症状 | 原因 | 解决 |
|------|------|------|
| akshare `Connection aborted` | push2.eastmoney.com:443 被封 | patch 到 push2delay |
| 腾讯接口返回空 | `parts[2]` 是纯代码 `002460`，不是 `sz002460` | 匹配时用纯代码 |
| 腾讯接口 `SOCKS support` 报错 | `trust_env=False` 导致系统代理强加 | 清除 `http_proxy` 环境变量 |
| ClawTeam `GitError: 无效引用 master` | workspace 分支是 `master` 不是 `main` | `git checkout -b main` |
| ClawTeam `duplicate session` | tmux session 名冲突 | `tmux kill-session -t <name>` |
| Alpha Vantage 返回 $0 | 免费key每日25次限额用完 | 等次日重置 |
