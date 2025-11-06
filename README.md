# 🎨 cq-tradingview-js
### TradingView‑Style Chart Renderer for JavaScript & TypeScript  
Part of the **CryptoQuantAI** Ecosystem

`cq-tradingview-js` is a lightweight, high‑performance JavaScript/TypeScript charting engine  
inspired by TradingView—designed for crypto dashboards, browser‑based platforms,  
automated report generation, and real‑time trading interfaces.

It works seamlessly with:
- **cq-indicators-js** (technical indicators)
- **cq-ohlcv-js** (future module)
- Web UIs, Node servers, and browser apps

---

## 🚀 Features

- ✅ TradingView‑style candlestick charts  
- ✅ Line / area / bar charts  
- ✅ Indicator overlays (EMA, RSI, MACD, Bollinger Bands…)  
- ✅ Multi‑panel layouts (Price · Volume · Indicators)  
- ✅ Fully customizable themes (dark, light, neon, minimalist)  
- ✅ Works in **Node.js** and **Browser**  
- ✅ Export charts as **PNG / JPEG / SVG**  
- ✅ Designed for real‑time dashboards  

Perfect for:
- Quant dashboards  
- Crypto trading bots  
- Browser‑based chart apps  
- Node.js analytics scripts  
- ML dataset image generation  

---

## 📦 Installation

```bash
npm install cq-tradingview-js
```

or

```bash
yarn add cq-tradingview-js
```

---

## 💡 Quick Start

### ✅ Create Candlestick Chart

```javascript
import { Chart } from "cq-tradingview-js";

const candles = [
  { time: 1710000000, open: 100, high: 105, low: 98, close: 103, volume: 1200 },
  { time: 1710000600, open: 103, high: 106, low: 102, close: 105, volume: 980 },
];

const chart = new Chart({
  width: 900,
  height: 500,
  theme: "dark",
});

chart.candles(candles);
chart.save("chart.png");
```

---

### ✅ Add Indicators

```javascript
import { Chart } from "cq-tradingview-js";
import { ema, rsi } from "cq-indicators-js";

const closes = candles.map(c => c.close);

const chart = new Chart();

chart.candles(candles);
chart.overlay("EMA 9", ema(closes, 9));
chart.overlay("EMA 21", ema(closes, 21));
chart.panel("RSI", rsi(closes, 14));

chart.save("indicators.png");
```

---

### ✅ Add Buy/Sell Markers

```javascript
chart.markers([
  { time: candles[10].time, price: candles[10].close, side: "buy" },
  { time: candles[30].time, price: candles[30].close, side: "sell" },
]);
```

---

## 🎨 Themes

Built‑in themes:

- `dark`
- `light`
- `clean`
- `neon`
- `classic`

Usage:

```javascript
const chart = new Chart({ theme: "neon" });
```

---

## 🗂 Folder Structure

```
cq-tradingview-js/
│
├── src/
│   ├── index.ts
│   ├── chart.ts
│   ├── renderer.ts
│   ├── panels.ts
│   ├── markers.ts
│   ├── themes/
│   │   ├── dark.ts
│   │   ├── light.ts
│   │   ├── neon.ts
│   │   ├── classic.ts
│   │
│   └── utils/
│       ├── scale.ts
│       ├── colors.ts
│       ├── math.ts
│
├── dist/
├── tests/
└── README.md
```

---

## 📅 Roadmap

- ✅ Multi‑chart grids  
- ✅ Indicator panels  
- ⏳ WebGPU‑accelerated renderer  
- ⏳ Live tick streaming overlays  
- ⏳ PineScript → JS converter  
- ⏳ Interactive browser mode  

---

## 🤝 Contributing

We welcome contributions!

Guidelines:
- Follow ESLint rules  
- Use Prettier formatting  
- Ensure TypeScript strict mode  
- Add unit tests for new features  

---

## ⚖️ License

MIT License — free for commercial and personal use.

---

## 👨‍💻 Maintained By

CryptoQuantAI Development Team
