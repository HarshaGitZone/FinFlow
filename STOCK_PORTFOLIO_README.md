# Stock Portfolio Tracker 📈

A comprehensive stock portfolio management system integrated into your LuiFlow financial tracking application.

## Features ✨

### 📊 Portfolio Management
- **Add Holdings**: Add stocks with symbol, name, quantity, buy price, and buy date
- **Real-time Prices**: Automatic price updates using Alpha Vantage API
- **Portfolio Summary**: View total invested, current value, P&L, and return percentage
- **Edit/Delete**: Full CRUD operations for your holdings

### 🔍 Stock Search & Discovery
- **Smart Search**: Search stocks by symbol or company name
- **Real-time Quotes**: Get current stock prices, changes, and volume
- **Company Details**: View comprehensive company information and description
- **Multiple Exchanges**: Support for NASDAQ, NYSE, LSE, NSE

### 📈 Interactive Charts
- **Portfolio Distribution**: Pie chart showing your holdings allocation
- **Performance Analysis**: Bar charts of best and worst performers
- **Value Comparison**: Visual representation of holdings by value
- **Top Holdings**: Chart of your largest investments

### 📊 Analytics & Insights
- **Top Performers**: Your best performing stocks
- **Worst Performers**: Stocks that need attention
- **Portfolio Distribution**: How your portfolio is allocated
- **Performance Metrics**: Detailed P&L analysis

## Setup Instructions 🚀

### 1. Backend Setup

1. **Get Alpha Vantage API Key**:
   - Visit [Alpha Vantage](https://www.alphavantage.co/support/#api-key)
   - Sign up for a free account
   - Get your API key (free tier: 25 requests/day, 5 requests/minute)

2. **Configure Environment**:
   ```bash
   cd backend
   cp .env.example .env
   # Edit .env and add your Alpha Vantage API key
   ```

3. **Install Dependencies**:
   ```bash
   cd backend
   npm install
   ```

4. **Start Backend Server**:
   ```bash
   npm start
   ```

### 2. Frontend Setup

1. **Install Dependencies** (if not already installed):
   ```bash
   cd frontend
   npm install
   ```

2. **Start Frontend**:
   ```bash
   npm run dev
   ```

3. **Access the Application**:
   - Open your browser and navigate to `http://localhost:5173`
   - Click on "Stocks" in the sidebar navigation

## Usage Guide 📖

### Adding Your First Stock

1. **Navigate to Stocks Page**: Click "Stocks" in the sidebar
2. **Click "Add Holding"**: Open the add holding modal
3. **Search for Stock**: Type company name or symbol (e.g., "Apple" or "AAPL")
4. **Select Stock**: Choose from search results
5. **Enter Details**:
   - **Quantity**: Number of shares you own
   - **Buy Price**: Price per share when you bought
   - **Buy Date**: Date of purchase
   - **Currency**: Trading currency (USD, EUR, etc.)
   - **Exchange**: Stock exchange
   - **Notes**: Optional notes about the investment

### Managing Your Portfolio

1. **View Holdings**: See all your stocks in the main table
2. **Update Prices**: Click "Update Prices" to refresh current market prices
3. **Edit Holdings**: Click the edit icon to modify details
4. **Delete Holdings**: Click the trash icon to remove stocks
5. **View Details**: Click the info icon to see company information

### Analytics & Charts

1. **View Charts**: Click "Charts" button to see visual analytics
2. **Portfolio Distribution**: See how your portfolio is allocated
3. **Performance Analysis**: Identify your best and worst performers
4. **Detailed Analytics**: Click "Analytics" for comprehensive insights

## API Endpoints 🔌

### Portfolio Management
- `GET /api/portfolio` - Get all holdings
- `POST /api/portfolio` - Add new holding
- `PUT /api/portfolio/:id` - Update holding
- `DELETE /api/portfolio/:id` - Delete holding
- `POST /api/portfolio/update-prices` - Update all prices
- `GET /api/portfolio/analytics` - Get portfolio analytics

### Stock Data
- `GET /api/stocks/search?keywords=...` - Search stocks
- `GET /api/stocks/quote/:symbol` - Get stock quote
- `GET /api/stocks/historical/:symbol` - Get historical data
- `GET /api/stocks/overview/:symbol` - Get company overview

## Data Model 📋

### Portfolio Holding Schema
```javascript
{
  symbol: String,        // Stock symbol (e.g., "AAPL")
  name: String,          // Company name (e.g., "Apple Inc.")
  quantity: Number,      // Number of shares
  buyPrice: Number,      // Purchase price per share
  buyDate: Date,         // Purchase date
  currentPrice: Number,  // Current market price
  currency: String,      // Trading currency
  exchange: String,      // Stock exchange
  notes: String,         // Optional notes
  lastUpdated: Date     // Last price update
}
```

## Rate Limits & Usage ⚠️

### Alpha Vantage Free Tier
- **25 requests per day**
- **5 requests per minute**
- **Stock quotes, search, and company data**

### Best Practices
1. **Update Prices Wisely**: Don't update prices too frequently
2. **Batch Updates**: Use the bulk update feature
3. **Cache Usage**: Prices are cached for 5 minutes
4. **Monitor Usage**: Track your API usage to avoid limits

## Features in Detail 🔍

### Real-time Price Updates
- Automatic price fetching when adding holdings
- Manual bulk price updates for all holdings
- Cached data to minimize API calls
- Error handling for API limits

### Smart Stock Search
- Search by company name or stock symbol
- Support for multiple exchanges
- Currency information
- Company type and region details

### Comprehensive Analytics
- Portfolio performance metrics
- Individual stock performance
- Allocation analysis
- P&L calculations and percentages

### Interactive Charts
- Responsive design for all screen sizes
- Multiple chart types (pie, bar, line)
- Real-time data updates
- Dark mode support

## Troubleshooting 🔧

### Common Issues

1. **API Key Issues**:
   - Ensure your Alpha Vantage API key is valid
   - Check if you've exceeded daily limits
   - Verify the key is properly set in .env file

2. **Price Update Failures**:
   - Rate limits may prevent updates
   - Try updating individual stocks instead of bulk
   - Check your internet connection

3. **Search Not Working**:
   - Verify API key permissions
   - Check if search keywords are valid
   - Ensure proper network connectivity

### Error Messages
- "No data found for symbol": Stock symbol may be invalid or delisted
- "API rate limit exceeded": You've hit the daily/minute limit
- "Failed to fetch stock data": Network or API issues

## Future Enhancements 🚀

### Planned Features
- [ ] Historical portfolio performance tracking
- [ ] Dividend tracking and reinvestment
- [ ] Watchlist functionality
- [ ] Price alerts and notifications
- [ ] Multiple portfolio support
- [ ] Export portfolio data
- [ ] Advanced filtering and sorting
- [ ] Sector allocation analysis
- [ ] Risk metrics and analysis

### API Improvements
- [ ] Multiple data source support
- [ ] Real-time WebSocket connections
- [ ] Enhanced caching strategies
- [ ] Offline mode support

## Support 📞

For issues or questions:
1. Check the troubleshooting section above
2. Verify your API key and network connection
3. Review the console for error messages
4. Ensure all dependencies are properly installed

---

**Happy Investing! 📈💰**
