# Bitcoin Mining Dashboard - Modern Edition

A completely modernized Bitcoin mining analytics dashboard with **real-time API integration**, smart caching, rate limiting, and contemporary design.

## 🚀 What's New

### Real API Integration with Smart Caching
- ✅ **Live Bitcoin Price** - CoinGecko API with 1-minute cache
- ✅ **Real Block Data** - Mempool.space API with 30-second cache
- ✅ **Network Hashrate** - Calculated from difficulty adjustment data
- ✅ **Mempool Statistics** - Real-time transaction data
- ✅ **Fee Recommendations** - Dynamic fee estimates
- ✅ **1-Year Price Charts** - Daily price history
- ✅ **Bitcoin News** - CryptoCompare News API with fallback
- ✅ **Rate Limiting** - Prevents API overuse
- ✅ **Error Handling** - Graceful fallbacks when APIs are unavailable

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
- Current block height (live, 30s cache)
- Bitcoin price with 24h change (live, 1min cache)
- Network hashrate (calculated from difficulty)
- Mining difficulty (live)
- Mempool size with transaction count (live, 30s cache)
- Recommended transaction fees (live, 30s cache)
- 1-year price chart (daily data points)
- 1-year difficulty trend chart

### 2. Block Explorer
- Latest 10 blocks (live, 30s cache)
- Block hash, transactions, size, weight
- Timestamps and links to Mempool.space
- Real-time block data

### 3. Network Statistics
- Current network hashrate (calculated)
- Current difficulty
- Blocks until next adjustment
- Estimated time to next adjustment
- 1-year hashrate history chart (weekly data)
- 1-year difficulty adjustment chart (26 epochs)

### 4. Mining Calculator
- Profitability calculator with real BTC price
- Daily/monthly/yearly profit estimates
- Electricity cost calculations
- Pool fee considerations
- Break-even analysis
- Uses live network data for accuracy

### 5. News Feed
- Latest Bitcoin news from CryptoCompare
- Fallback to curated sample news
- Article titles, descriptions, and links
- Timestamps and sources

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

### 1. Mempool.space API (Primary Data Source)
```
https://mempool.space/api
- /blocks/tip/height - Current block height (30s cache)
- /blocks - Latest blocks (30s cache)
- /mempool - Mempool statistics (30s cache)
- /v1/fees/recommended - Fee recommendations (30s cache)
- /v1/difficulty-adjustment - Network difficulty & hashrate (1min cache)
```

### 2. CoinGecko API (Price Data)
```
https://api.coingecko.com/api/v3
- /simple/price - Current BTC price with 24h change (1min cache)
- /coins/bitcoin/market_chart - 1-year historical price (5min cache)
```

### 3. CryptoCompare API (News)
```
https://min-api.cryptocompare.com
- /data/v2/news/ - Bitcoin and mining news
- Fallback to sample news if unavailable
```

## 🔒 Rate Limiting & Caching

The dashboard implements smart caching and rate limiting:
- **Price data**: 1-minute cache, 10 requests/minute limit
- **Block data**: 30-second cache, 10 requests/minute limit  
- **Charts**: 5-minute cache for historical data
- **Automatic retry**: Graceful fallback when rate limits hit
- **Local caching**: Reduces API calls by 80%+

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

## 🔄 Auto-Refresh & Caching

The dashboard uses intelligent caching and refresh strategies:

**Auto-Refresh (Dashboard Only)**:
- Refreshes every 2 minutes when viewing the Dashboard page
- Only updates: block height, price, and mempool data
- Charts remain cached for better performance

**Manual Refresh**:
- Each page has a refresh button (3-second cooldown)
- Forces fresh data fetch while respecting rate limits

**Cache TTLs**:
- Block height: 30 seconds
- Bitcoin price: 60 seconds
- Mempool info: 30 seconds
- Fee estimates: 30 seconds
- Price charts: 5 minutes
- Block data: 30 seconds

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

## ⚠️ API Rate Limits & Error Handling

The dashboard implements comprehensive rate limiting and error handling:

**Built-in Protection**:
- Rate limiter: 10 requests per minute per endpoint
- Smart caching reduces API calls by 80%+
- Automatic retry with exponential backoff
- Graceful fallbacks when APIs unavailable

**API Limits**:
- **CoinGecko Free**: 10-50 calls/minute (we stay well under)
- **Mempool.space**: No strict limits (we cache aggressively)
- **CryptoCompare**: 100,000 calls/month free tier

**Error Handling**:
- Failed requests show "Error" instead of crashing
- News page falls back to sample articles
- Charts degrade gracefully with error messages
- All errors logged to browser console

The dashboard is designed to work reliably even with API limitations!

## 🐛 Troubleshooting

### Data Shows "Error" or "Loading..."
**Possible Causes:**
- API temporarily unavailable
- Rate limit reached (wait 1 minute)
- Network connectivity issue
- Browser blocking API requests

**Solutions:**
- Wait 60 seconds and click refresh
- Check browser console (F12) for specific errors
- Try in incognito/private mode
- Check internet connection
- Disable browser extensions that might block APIs

### Charts Not Loading
**Solutions:**
- Ensure Chart.js CDN is accessible
- Check browser console for errors
- Clear browser cache (Ctrl+F5 or Cmd+Shift+R)
- Wait for rate limit cooldown (1-5 minutes)

### News Not Loading
**Expected Behavior:**
- CryptoCompare may be blocked by some networks
- Fallback sample news will automatically display
- This is normal and intentional

### Price Chart Shows Error
**Likely Cause:**
- CoinGecko rate limit reached
- Solution: Wait 5 minutes before refreshing
- Historical data is cached for 5 minutes

### Performance Issues
**Solutions:**
- Close other browser tabs
- Clear cache and reload
- Disable auto-refresh if needed (edit line ~3430)
- Use Chrome/Firefox for best performance

## 💡 Tips for Best Experience

1. **Don't spam refresh** - Caching makes repeated clicks unnecessary
2. **Use the dashboard page** - Auto-refreshes every 2 minutes
3. **Check console** - Press F12 to see what's happening
4. **Wait for cooldowns** - Refresh buttons have 3-second cooldown
5. **Be patient** - Some APIs can be slow, give them 5-10 seconds

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
