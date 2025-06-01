# ⚡ TSLA Professional Trading Dashboard

A comprehensive Tesla stock analysis dashboard built with Streamlit, featuring TradingView-style charts, AI-powered analysis, and interactive replay functionality.

## ✨ Features

### 📊 Interactive Trading Chart
- **TradingView-style candlestick charts** with professional dark theme
- **Support and resistance zones** visualization
- **Trading signals** (LONG/SHORT/Neutral) with visual markers
- **Multiple timeframes** (1D, 1W, 1M, 3M, 1Y, ALL)
- **Real-time filtering** and responsive design

### 🤖 AI-Powered Analysis
- **Gemini AI integration** for intelligent data analysis
- **Natural language queries** about your stock data
- **Pre-built sample questions** for quick insights
- **Chat history** to track your analysis sessions
- **Automated insights** on trading patterns and performance

### ▶️ Chart Replay Feature
- **Time-based replay** of historical price action
- **Variable speed control** (0.5x to 10x speed)
- **Progress tracking** with visual indicators
- **Pause/Resume** functionality for detailed analysis

### 📈 Market Overview
- **Key metrics dashboard** with trading statistics
- **Performance indicators** and price change tracking
- **Signal distribution** analysis (Long vs Short vs Neutral)
- **Volume analysis** and trading day statistics

## 🚀 Installation

### Prerequisites
- Python 3.8 or higher
- pip package manager

### Setup Instructions

1. **Clone or download the project files**
   ```bash
   # If using git
   git clone <repository-url>
   cd tsla-dashboard
   
   # Or download and extract the files
   ```

2. **Install required packages**
   ```bash
   pip install -r requirements.txt
   ```

3. **Configure Gemini AI (Required for AI features)**
   - Get your Gemini API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
   - Replace the hardcoded API key in `eg.py` line 289:
   ```python
   api_key = "YOUR_ACTUAL_GEMINI_API_KEY_HERE"
   ```

4. **Run the application**
   ```bash
   streamlit run eg.py
   ```

5. **Access the dashboard**
   - Open your browser and navigate to `http://localhost:8501`

## 📁 Data Format

### CSV File Structure
Your TSLA data CSV should contain the following columns:

| Column | Type | Description | Required |
|--------|------|-------------|----------|
| Date | datetime | Trading date (YYYY-MM-DD) | ✅ Yes |
| Open | float | Opening price | ✅ Yes |
| High | float | Highest price of the day | ✅ Yes |
| Low | float | Lowest price of the day | ✅ Yes |
| Close | float | Closing price | ✅ Yes |
| Volume | integer | Trading volume | ✅ Yes |
| direction | string | Trading signal ('LONG', 'SHORT', 'N') | ✅ Yes |
| Support | list/string | Support levels (e.g., "[180.5, 175.2]") | ⚠️ Optional |
| Resistance | list/string | Resistance levels (e.g., "[220.8, 225.4]") | ⚠️ Optional |

### Sample Data Row
```csv
Date,Open,High,Low,Close,Volume,direction,Support,Resistance
2024-01-15,195.50,198.75,192.30,196.80,12500000,LONG,"[185.2, 180.5]","[205.8, 210.4]"
```

## 🎯 Usage Guide

### 1. Loading Data
- **Upload CSV**: Use the sidebar file uploader to load your TSLA data
- **Demo Mode**: Run without uploading to see sample data
- **Data Validation**: The app automatically validates required columns

### 2. Chart Analysis
- **Time Periods**: Click buttons (1D, 1W, 1M, 3M, 1Y, ALL) to filter data
- **Visual Signals**: 
  - 🟢 **Green arrows up**: LONG signals
  - 🔴 **Red arrows down**: SHORT signals  
  - 🟡 **Yellow dots**: Neutral signals
- **Support/Resistance**: Green and red shaded zones show key levels

### 3. AI Analysis
- **Sample Questions**: Click pre-built questions for quick insights
- **Custom Queries**: Type your own questions about the data
- **Chat History**: Review previous AI responses
- **Example Questions**:
  - "How many days in 2023 was TSLA bullish?"
  - "What was the highest closing price and when did it occur?"
  - "Which month had the most volatile price movements?"

### 4. Chart Replay
- **Speed Control**: Adjust replay speed from 0.5x to 10x
- **Controls**: Start/Pause, Reset functionality
- **Progress**: Visual progress bar and day counter

## 🛠️ Technical Details

### Architecture
- **Frontend**: Streamlit with custom CSS styling
- **Charts**: streamlit-lightweight-charts for TradingView-style visualization
- **AI Engine**: Google Gemini AI for natural language analysis
- **Data Processing**: Pandas and NumPy for data manipulation

### Key Components
- **TSLADashboard Class**: Main application logic
- **Chart Generation**: Dynamic candlestick chart creation
- **Data Filtering**: Time-based data filtering system
- **AI Integration**: Gemini AI query processing
- **State Management**: Streamlit session state for replay functionality

## 🔧 Customization

### Styling
The dashboard uses a professional dark theme with TradingView-inspired colors:
- **Background**: Deep blue (#0f0f23)
- **Accent**: Cyan (#00d4aa)
- **Bull/Long**: Green (#00d4aa)
- **Bear/Short**: Red (#ff4976)

### Extending Functionality
- **Add new indicators**: Modify the chart creation function
- **Custom AI prompts**: Enhance the AI query system
- **Additional timeframes**: Add new filtering options
- **Export features**: Add data download capabilities

## ⚠️ Important Notes

### Security
- **API Key**: Never commit your Gemini API key to version control
- **Environment Variables**: Consider using environment variables for API keys:
  ```python
  import os
  api_key = os.getenv('GEMINI_API_KEY')
  ```

### Performance
- **Large Datasets**: Performance may vary with very large datasets (>10K rows)
- **Replay Speed**: Higher speeds may cause browser performance issues
- **Memory Usage**: Monitor memory usage with large CSV files

### Limitations
- **Data Dependencies**: Requires properly formatted CSV data
- **AI Rate Limits**: Gemini AI has usage limits
- **Browser Compatibility**: Best viewed in modern browsers (Chrome, Firefox, Safari)

## 🐛 Troubleshooting

### Common Issues

1. **"No module named 'streamlit'"**
   ```bash
   pip install streamlit
   ```

2. **"API key error"**
   - Verify your Gemini API key is correct
   - Check API key permissions and quotas

3. **"CSV format error"**
   - Ensure your CSV has the required columns
   - Check date format (YYYY-MM-DD)

4. **Chart not displaying**
   - Check browser console for JavaScript errors
   - Try refreshing the page

### Getting Help
- Check the Streamlit documentation: https://docs.streamlit.io/
- Gemini AI documentation: https://ai.google.dev/docs
- Create an issue in the project repository

## 📜 License

This project is provided as-is for educational and personal use. Please ensure compliance with relevant financial data regulations in your jurisdiction.

## 🤝 Contributing

Feel free to submit issues, feature requests, or pull requests to improve the dashboard.

---

**Happy Trading! 📈⚡** #
