# trmp-crpt

Reads crypto market data alongside social media posts and generates buy/sell signals.

## Structure

```
backend/    Go service + CLI tool (trmpcrpt-cli)
frontend/   React/JS UI
```

## Backend

The backend that reads market data along with social media posts. The sentiment of the social media posts along with the market data is used to generate buy/sell signals. The backend exposes a REST api along with a streaming data.

**Supported coins:** 
- BTC
- ETH
- SOL
- BNB

**Market data providers:** 
- [CoinLore](https://www.coinlore.com/cryptocurrency-data-api) (default provider)

**Data per coin:**
- Price (USD)
- 24h and 7d percent change
- Market cap and volume

### Key interfaces

```go
type MarketProvider interface {
    Fetch(ctx context.Context, coins []string) ([]CoinData, error)
}

func New(coins []string, provider MarketProvider, interval time.Duration) *MarketReader
func (r *MarketReader) Subscribe() <-chan CoinData
func (r *MarketReader) Unsubscribe(ch <-chan CoinData)
func (r *MarketReader) Start(failTimeout time.Duration)
```

## Frontend

React/JS app displaying market data and buy/sell signals.

## Running

```sh
cd backend && go run .
cd frontend && npm install && npm start
```

