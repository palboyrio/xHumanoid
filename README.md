# xHumanoid: AI-Powered Crypto Trading Platform

xHumanoid is an advanced AI-driven cryptocurrency trading platform that leverages multiple state-of-the-art language models to analyze market data and execute trades with precision.

### Overview

- Multi-Model AI: 6 AI models work together for optimal trading decisions.
- Real-Time Analysis: Live market data processed every 30 seconds.
- Risk Management: Advanced position sizing and stop-loss strategies.

### AI Models

- Claude Sonnet 4.5: Complex reasoning, long-term trend analysis.
- DeepSeek V3.2: Pattern recognition, chart formations.
- Gemini 2.5 PRO: Multi-modal market intelligence.
- Grok 4: Real-time sentiment analysis.
- GPT-5: Conual prediction.
- Qwen 3-Max: High-frequency trading signals.

### Trading System

- Signal Types: LONG, SHORT, HOLD, WAIT, CLOSE (with confidence scores).
- Risk Management Formula:
  - Base risk % (5-15%) based on confidence.
  - Leverage and position sizing with max exposure constraint (≤ 65%).
- Trade Duration Logic: From quick scalps (15min) to major trend plays (2-8h).
- Stop Loss & Take Profit: Adaptive placement based on volatility and market structure.

### Setup & Installation

#### Requirements

- Python 3.10 or higher
- Node.js 18+ and npm
- Next.js (latest version)
- API keys for AI model providers (Claude, OpenAI, etc.)
- Aster API credentials
- HTTPS-enabled domain

Clone repository
git clone https://github.com/yourusername/xhumanoid.git

Configure database
mysql -u root -p < database/schema.sql

Set up configuration
cp data/config.example.php data/config.php

Edit configuration file with your API keys
nano data/config.php

Set permissions
chmod 755 aiagent/
chmod 644 data/config.php



### Configuration

Edit `data/config.php` with your settings:

return [
'site_enabled' => true,
'github_link' => 'https://github.com/yourusername/xhumanoid',
'twitter_link' => 'https://twitter.com/yourhandle',
// AI Model API Keys
'claude_api_key' => 'sk-ant-api03-...',
'openai_api_key' => 'sk-...',
'anthropic_version' => '2023-06-01',
// Trading Configuration
'Aster_api_key' => 'your_Aster_key',
'Aster_api_secret' => 'your_Aster_secret',
'max_position_exposure' => 0.65, // 65%
'update_interval' => 30, // seconds
];



### Running the System

Start the trading bot
php aiagent/trading_bot.php

Run in background (Linux)
nohup php aiagent/trading_bot.php > logs/bot.log 2>&1 &

Monitor logs
tail -f logs/bot.log



### API Reference

- Base URL: https://api.0xxhumanoid.ai/v1

#### Authentication

All requests require an API key:

- Authorization: Bearer YOUR_API_KEY
- Content-Type: application/json

#### Endpoints

- POST /api/analyze: Analyze market and get AI trading recommendations.
- GET /api/market/{symbol}: Get market data for a symbol.
- GET /api/positions: List active trading positions.
- POST /api/trade: Execute a trade.
- DELETE /api/positions/{position_id}: Close a position.
- GET /api/history: Get trading history.

#### Example: Python

import requests

def get_positions():
url = 'https://api.0xxhumanoid.ai/v1/api/positions'
headers = {
'Authorization': 'Bearer YOUR_API_KEY',
'Content-Type': 'application/json'
}
response = requests.get(url, headers=headers)
data = response.json()
for position in data['positions']:
print(f"Symbol: {position['symbol']}")
print(f"P&L: {position['pnl_percentage']}%")
print("---")

get_positions()



### Support & Resources

- Documentation: Comprehensive guides and tutorials
- API Reference: Complete API documentation
- Community: Join our developer community (Discord)

### License

© 2025 xHumanoid. All rights reserved.
You can copy and paste this directly into your README.md—it's fully formatted for markdown.


#### Installation Steps

