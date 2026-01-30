# AI 热点自动监控

自动监控 Twitter 上 AI 领域博主的推文，使用 AI 总结后推送到飞书。

## 配置

### 1. config.py - Twitter 监控配置

```python
TWITTER_API_KEY = "你的API密钥"  # 从 twitterapi.io 获取
WATCHED_ACCOUNTS = ["OpenAI", "AnthropicAI", ...]  # 要监控的账号
MONITOR_INTERVAL_SECONDS = 3600  # 监控间隔（秒）
```

### 2. summarizer_config.py - AI 总结配置

```python
API_BASE_URL = "https://api.openai.com/v1"  # OpenAI 兼容接口
API_KEY = "你的API密钥"
MODEL = "gpt-4o-mini"  # 模型名称
```

### 3. feishu_config.py - 飞书推送配置（可选）

```python
APP_ID = "你的应用ID"
APP_SECRET = "你的应用Secret"
CHAT_ID = "群聊ID"
```

## 运行

```bash
# 安装依赖
pip install -r requirements.txt

# 运行一次监控
python twitter_monitor.py --once

# 持续监控
python twitter_monitor.py

# AI 总结
python summarizer.py

# 推送到飞书
python feishu_sender.py --latest
```
