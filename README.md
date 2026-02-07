# Bitcoin Mining Dashboard - Modern Edition

A completely modernized Bitcoin mining analytics dashboard with **real-time API integration** and contemporary design.

## 🚀 What's New

### Real API Integration
- ✅ **Live Bitcoin Price** - CoinGecko API
- ✅ **Real Block Data** - Mempool.space API
- ✅ **Network Hashrate** - Blockchain.info API
- ✅ **Mempool Statistics** - Real-time transaction data
- ✅ **Fee Recommendations** - Dynamic fee estimates
- ✅ **24-Hour Price Charts** - Hourly price updates
- ✅ **Bitcoin News** - CoinGecko news feed

### Modern Design Features
- 🎨 **Contemporary UI** - Clean, professional design with Inter font
- 🌈 **Animated Background** - Subtle gradient animations
- 📱 **Fully Responsive** - Works on all devices
- ⚡ **Fast Performance** - Optimized API calls with caching
- 🔄 **Auto-Refresh** - Updates every 60 seconds
- 📊 **Interactive Charts** - Chart.js 4.4.0 with modern styling
- 🎯 **Smooth Animations** - CSS transitions and hover effects

## 📋 Features

### 1. Dashboard Page
- Current block height (live)
- Bitcoin price with 24h change (live)
- Network hashrate (live)
- Mining difficulty (live)
- Mempool size (live)
- Recommended transaction fees (live)
- 24-hour price chart (live data)
- 7-day hashrate chart

### 2. Block Explorer
- Latest 10 blocks (live)
- Block hash, transactions, size, weight
- Timestamps and links to Mempool.space
- Real-time block data

### 3. Network Statistics
- Current network hashrate
- 30-day average hashrate
- Hashrate trend analysis
- Next difficulty adjustment estimate
- 30-day hashrate history chart
- Difficulty adjustment chart

### 4. Mining Calculator
- Profitability calculator with real BTC price
- Daily/monthly/yearly profit estimates
- Electricity cost calculations
- Pool fee considerations
- Break-even analysis
- Uses live network data for accuracy

### 5. News Feed
- Latest Bitcoin news from CoinGecko
- Article titles, descriptions, and links
- Timestamps and sources
- Fallback to sample news if API unavailable

## 🛠️ Technologies Used

- **HTML5** - Modern semantic markup
- **CSS3** - Custom properties, Grid, Flexbox
- **Vanilla JavaScript** - No frameworks needed
- **Chart.js 4.4.0** - Beautiful responsive charts
- **Multiple APIs**:
  - Mempool.space (blocks, mempool, fees)
  - CoinGecko (price, news)
  - Blockchain.info (hashrate, difficulty)

## 🌐 APIs Used

### 1. Mempool.space API
```
https://mempool.space/api
- /blocks/tip/height - Current block height
- /blocks - Latest blocks
- /mempool - Mempool statistics
- /v1/fees/recommended - Fee recommendations
```

### 2. CoinGecko API
```
https://api.coingecko.com/api/v3
- /simple/price - Current BTC price
- /coins/bitcoin/market_chart - Historical price data
- /news - Bitcoin news
```

### 3. Blockchain.info API
```
https://blockchain.info
- /q/hashrate - Network hashrate
- /q/getdifficulty - Current difficulty
```

## 📦 Installation

### Option 1: Simple Setup
1. Download the `index.html` file
2. Open it in any modern web browser
3. That's it! No server required.

### Option 2: GitHub Pages
1. Create a repository named `yourusername.github.io`
2. Upload `index.html`
3. Go to Settings → Pages
4. Select main branch as source
5. Visit `https://yourusername.github.io`

### Option 3: Local Server
```bash
# Python
python -m http.server 8000

# Node.js
npx http-server
```

Then open `http://localhost:8000`

## ⚙️ Configuration

All API endpoints are configured at the top of the `<script>` section:

```javascript
const MEMPOOL_API = 'https://mempool.space/api';
const COINGECKO_API = 'https://api.coingecko.com/api/v3';
const BLOCKCHAIN_API = 'https://blockchain.info';
```

## 🔄 Auto-Refresh

The dashboard automatically refreshes data every 60 seconds when viewing the Dashboard page. You can also manually refresh using the refresh buttons on each page.

## 🎨 Customization

### Colors
Edit the CSS variables at the top of the `<style>` section:

```css
:root {
    --bg-primary: #0a0e27;
    --bg-secondary: #141b2d;
    --bg-card: #1a1f37;
    --accent-orange: #f7931a;
    --accent-green: #00d395;
    --accent-blue: #5b8def;
    --text-primary: #e8eaed;
    --text-secondary: #9aa0b2;
}
```

### Fonts
The dashboard uses Inter font from Google Fonts. You can change this in the `<head>` section.

## 📊 Data Accuracy

All data is fetched in real-time from reliable APIs:
- **Price data**: Updated every minute
- **Block data**: Real-time from Mempool.space
- **Hashrate**: Live from Blockchain.info
- **Charts**: Use real historical data

## ⚠️ API Rate Limits

The APIs used have the following limits:
- **CoinGecko**: 10-50 calls/minute (free tier)
- **Mempool.space**: No strict limits
- **Blockchain.info**: No strict limits

The dashboard is optimized to stay within these limits with caching and smart refresh intervals.

## 🐛 Troubleshooting

### Charts Not Loading
- Check browser console for errors
- Ensure Chart.js CDN is accessible
- Clear browser cache

### Data Shows "Error"
- Check internet connection
- API might be temporarily down
- Check browser console for specific errors
- Try the refresh button

### News Not Loading
- CoinGecko news API might be unavailable
- Fallback sample news will display
- Check browser console for errors

## 🔮 Future Enhancements

Potential features to add:
- Mining pool statistics
- Historical difficulty adjustments
- Fee rate predictions
- Network transaction volume
- Lightning Network stats
- More detailed mempool analysis
- User preferences/settings
- Dark/light theme toggle
- Export data to CSV

## 📱 Browser Support

- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+

## 📄 License

Free to use and modify. Attribution appreciated but not required.

## 🙏 Credits

- **APIs**: Mempool.space, CoinGecko, Blockchain.info
- **Charts**: Chart.js
- **Design**: Custom modern design
- **Font**: Inter by Rasmus Andersson

---

**Built with ❤️ for the Bitcoin mining community**

Made by: Your Name
Last Updated: February 2026
