# AI Quantitative Trading Terminal

A real-time AI-powered quantitative trading laboratory capable of streaming institutional-grade candlestick charts, analyzing live market behavior, and generating probabilistic next-candle directional predictions.

## Tech Stack

### Frontend
- Next.js 14 with TypeScript
- Tailwind CSS
- TradingView Lightweight Charts
- WebSockets for real-time data
- React Query for state management

### Backend
- FastAPI (Python)
- WebSockets for streaming
- Redis for caching
- PostgreSQL/TimescaleDB for time-series data
- PyTorch/TensorFlow for AI models
- NumPy/Pandas for data processing
- Scikit-learn for ML models

## Project Structure

```
.
├── frontend/                    # Next.js frontend application
│   ├── src/
│   │   ├── app/                # Next.js app directory
│   │   ├── components/         # React components
│   │   ├── hooks/              # Custom React hooks
│   │   ├── lib/                # Utility functions
│   │   └── types/              # TypeScript type definitions
│   ├── package.json
│   ├── tsconfig.json
│   └── tailwind.config.ts
├── backend/                     # FastAPI backend services
│   ├── app/
│   │   ├── models/             # Pydantic models
│   │   ├── routers/            # API routes
│   │   └── services/           # Business logic
│   │       ├── market_feed.py
│   │       ├── candle_aggregator.py
│   │       ├── ai_predictor.py
│   │       ├── quantitative_analytics.py
│   │       ├── feature_engineering.py
│   │       ├── ml_models.py
│   │       ├── pattern_recognition.py
│   │       └── websocket_manager.py
│   ├── main.py
│   └── requirements.txt
├── docker-compose.yml           # Container orchestration
├── package.json                 # Root package.json
└── README.md
```

## Features

- Real-time candlestick chart rendering
- Multi-asset market streaming (Forex, Crypto, Commodities, Stocks)
- Dynamic timeframe generation (5s to 1d)
- AI prediction overlays with ensemble models
- Pattern recognition (engulfing, pin bars, doji, breakouts)
- Quantitative analytics (RSI, MACD, EMA, VWAP, ATR, Bollinger Bands)
- Live candle countdown system
- Crosshair tracking and price markers
- Trade visualization markers
- High-frequency update pipelines
- Ensemble ML forecasting (LSTM, Transformer, CNN)
- Feature engineering pipeline
- WebSocket real-time streaming

## Getting Started

### Prerequisites
- Node.js 18+
- Python 3.11+
- Redis (optional, for production caching)
- PostgreSQL (optional, for production storage)

### Installation

1. **Clone the repository and navigate to the project directory**

2. **Install root dependencies:**
```bash
npm install
```

3. **Install frontend dependencies:**
```bash
cd frontend
npm install
```

4. **Install backend dependencies:**
```bash
cd ../backend
pip install -r requirements.txt
```

5. **Set up environment variables:**
```bash
# Frontend
cd frontend
cp .env.example .env.local
# Edit .env.local with your configuration

# Backend
cd ../backend
cp .env.example .env
# Edit .env with your configuration
```

6. **Start Redis and PostgreSQL (optional, for production):**
```bash
docker-compose up -d
```

7. **Run the development servers:**

Option 1: Run both frontend and backend together
```bash
cd ..
npm run dev
```

Option 2: Run separately
```bash
# Terminal 1 - Frontend
cd frontend
npm run dev

# Terminal 2 - Backend
cd backend
python main.py
```

### Access the Application

- **Frontend**: http://localhost:3000
- **Backend API**: http://localhost:8000
- **API Documentation**: http://localhost:8000/docs
- **WebSocket**: ws://localhost:8000/ws

## Usage

1. **Select a Market Pair**: Choose from Forex, Crypto, Commodities, or Stocks
2. **Select a Timeframe**: Choose from 5s to 1d timeframes
3. **View Real-Time Charts**: Watch candles update in real-time
4. **AI Predictions**: View AI-generated predictions with confidence scores
5. **Analytics**: Monitor technical indicators and market statistics

## Architecture

The platform is divided into 15 major systems:

1. **Real-Time Market Feed Engine**: Streams live market prices
2. **Candle Aggregation Engine**: Converts ticks to OHLC candles
3. **Chart Rendering Engine**: Renders institutional-grade charts
4. **AI Prediction Engine**: Ensemble ML forecasting
5. **Pattern Recognition Engine**: Detects candlestick patterns
6. **Timeframe Synchronization Engine**: Manages multiple timeframes
7. **Market Pair Selection Engine**: Handles asset switching
8. **Trade Visualization Layer**: Displays trade markers
9. **WebSocket Streaming Layer**: Real-time data delivery
10. **Prediction Overlay System**: Displays AI predictions
11. **Quantitative Analytics Engine**: Calculates technical indicators
12. **Historical Data Storage Layer**: Stores market data
13. **Reinforcement Learning Pipeline**: Adaptive learning
14. **Ensemble Forecasting Framework**: Combines multiple models
15. **Frontend Trading Interface**: User interface

## API Endpoints

### Market Data
- `GET /api/market/pairs` - Get all market pairs
- `GET /api/market/pairs/{symbol}` - Get specific pair

### Predictions
- `GET /api/predictions/current/{pair}` - Get current prediction

### WebSocket
- `WS /ws` - Real-time market data streaming

## Development

### Frontend Development
```bash
cd frontend
npm run dev
```

### Backend Development
```bash
cd backend
python main.py
```

### Running Tests
```bash
# Frontend tests
cd frontend
npm test

# Backend tests
cd backend
pytest
```

## Production Deployment

### Docker Deployment
```bash
docker-compose up -d
```

### Manual Deployment
1. Build frontend: `cd frontend && npm run build`
2. Start backend: `cd backend && uvicorn main:app --host 0.0.0.0 --port 8000`
3. Use nginx as reverse proxy for frontend

## Configuration

### Frontend (.env.local)
```
NEXT_PUBLIC_API_URL=http://localhost:8000
NEXT_PUBLIC_WS_URL=ws://localhost:8000/ws
```

### Backend (.env)
```
REDIS_URL=redis://localhost:6379
DATABASE_URL=postgresql://trading_user:trading_password@localhost:5432/trading_terminal
API_HOST=0.0.0.0
API_PORT=8000
```

## License

MIT

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

## Support

For issues and questions, please open an issue on the repository.
