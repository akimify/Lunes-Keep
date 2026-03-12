# 🖥️ Lunes-Keep

自动登录保活 Lunes 免费服务器，每 10 天定时运行。

## 🔐 Secrets 配置

**Settings → Secrets and variables → Actions → New repository secret** 添加以下变量：

| Secret 名 | 说明 | 示例 |
|---|---|---|
| `LUNES_ACCOUNTS` | 🧾 账号配置，JSON 数组格式 | 见下方 |
| `TG_BOT` | 📨 Telegram 推送，Chat ID 和 Bot Token 用英文逗号分隔 | `987654321,123456:AAFxxx` |
| `PRIVATE_REPO_TOKEN` | 🔑 有私库读取权限的 GitHub PAT | `github_pat_xxxxxx` |

## 📋 LUNES_ACCOUNTS 格式

```json
[
  {
    "note": "账号1-备注",
    "email": "your@email.com",
    "password": "yourpassword",
    "target_url": "https://betadash.lunes.host/servers/12345",
    "proxy": "socks5://user:pass@1.2.3.4:1080"
  },
  {
    "note": "账号2-备注",
    "email": "your2@email.com",
    "password": "yourpassword2",
    "target_url": "https://betadash.lunes.host/servers/67890",
    "proxy": "socks5://user:pass@2.3.4.5:1080"
  }
]
```

## 📝 PRIVATE_REPO_TOKEN 生成方式

GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic) → Generate new token (classic) → 勾选 `repo` + `workflow` → Generate token → 填入 Secret。
