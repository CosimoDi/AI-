# AI 热点自动监控

观众基于bilibili@人工大黑在 https://anxiety.daheiai.com/ 开源的项目，做二次开发。若有侵权请联系微信：CJHdhxsj1101

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

# 修改原因：将python命令替换为Python 3.11绝对路径，规避环境冲突，解决ModuleNotFoundError问题
pip install -r requirements.txt
C:\Users\陈景鸿\AppData\Local\Programs\Python\Python311\python.exe twitter_monitor.py --once
C:\Users\陈景鸿\AppData\Local\Programs\Python\Python311\python.exe twitter_monitor.py

C:\Users\陈景鸿\AppData\Local\Programs\Python\Python311\python.exe summarizer.py
C:\Users\陈景鸿\AppData\Local\Programs\Python\Python311\python.exe feishu_sender.py --latest