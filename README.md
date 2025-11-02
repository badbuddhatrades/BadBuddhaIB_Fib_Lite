# BadBuddha IB Fib Extensions Lite

<div align="center">

![Version](https://img.shields.io/badge/version-v1.0.0.0-blue)
![Platform](https://img.shields.io/badge/platform-NinjaTrader%208-green)
![License](https://img.shields.io/badge/license-Free-brightgreen)
![Edition](https://img.shields.io/badge/edition-Lite-yellow)
![Release](https://img.shields.io/badge/release-September%202025-lightgrey)

**Free Initial Balance indicator with Fibonacci extensions for day traders**

[Features](#-key-features) • [Installation](#-installation) • [Configuration](#-configuration-guide) • [Upgrade to PRO](#-upgrade-to-pro) • [Support](#-support--updates)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [Screenshots](#-screenshots)
- [Installation](#-installation)
- [Configuration Guide](#-configuration-guide)
  - [Initial Balance Settings](#initial-balance-settings)
  - [Style Settings](#style-settings)
  - [Update Settings](#update-settings)
- [How It Works](#-how-it-works)
- [Use Cases](#-use-cases)
- [Lite vs PRO Comparison](#-lite-vs-pro-comparison)
- [Troubleshooting](#-troubleshooting)
- [Tips & Best Practices](#-tips--best-practices)
- [Upgrade to PRO](#-upgrade-to-pro)
- [Support & Updates](#-support--updates)

---

## 🎯 Overview

**BadBuddha IB Fib Extensions Lite** is a **free** NinjaTrader 8 indicator that plots the Initial Balance (IB) range with industry-standard Fibonacci extension levels. Perfect for day traders who want clean IB visualization without the complexity of customization.

### Version Information

| Info | Details |
|------|---------|
| **Version** | v1.0.0.0 |
| **Release Date** | September 8, 2025 |
| **Edition** | Lite (Free) |
| **Author** | BadBuddha Customs LLC |
| **License** | Free |

---

## ✨ Key Features

### 1. **Initial Balance Calculation**

The indicator automatically calculates the high/low range during the opening period:

- ✅ **Default Duration**: 60 minutes (customizable)
- ✅ **Start Time**: 09:30 by default (configurable)
- ✅ **Session Anchoring**: Choose calendar day or trading session
- ✅ **Automatic Reset**: New IB every session/day

### 2. **Visual IB Range**

Clear visualization of the Initial Balance:

| Element | Description |
|---------|-------------|
| **IB Rectangle** | Shaded box showing the IB range |
| **IB High/Low Lines** | Horizontal lines at range boundaries |
| **50% Midline** | Optional equilibrium line |
| **Clean Labels** | Clear text markers on the right |

### 3. **Fixed Fibonacci Extensions** ⭐

The Lite version includes **3 proven Fibonacci levels**:

```
0.5    → 50% extension (half IB range)
1.0    → 100% extension (1x IB range)
1.618  → Golden ratio extension
```

These levels project both:
- 📈 **Upward** from IB High
- 📉 **Downward** from IB Low

### 4. **Full Color Customization**

Despite being free, Lite offers complete color control:

- 🎨 IB High/Low line color
- 🎨 Midline color
- 🎨 Extension up line color
- 🎨 Extension down line color
- 🎨 Rectangle fill color with opacity control (0-100%)

### 5. **Clean Label Display**

Professional labels with format:
```
IB High          → Main IB boundary
IB Low           → Main IB boundary
IB 50%           → Midline
IB + 0.5R        → Upward extensions
IB + 1R
IB + 1.618R
IB - 0.5R        → Downward extensions
IB - 1R
IB - 1.618R
```

### 6. **Flexible Session Settings**

Control how IB resets:

| Mode | Resets At | Best For |
|------|-----------|----------|
| **Calendar Day** | Midnight (00:00) | 24-hour markets (Forex, Crypto) |
| **Session** | Trading session open | Futures, Equities (e.g., ES 18:00) |

### 7. **Automatic Update Checker**

Built-in update notifications:

- 📅 Checks every **7 days**
- 🔔 Optional popup notifications
- 📄 Shows changelog and version info
- ⚙️ Can be disabled

---

## 📸 Screenshots

### Single IB Block with Extensions
*Example showing IB range with 0.5, 1.0, and 1.618 Fibonacci levels*

![IB Range Example](screenshots/lite-ib-range.png)

> **Note**: Shows IB High/Low, 50% midline, and extension levels

### Clean Chart Integration
*Lite version integrates seamlessly with your chart theme*

![Chart Integration](screenshots/lite-chart-integration.png)

> Customizable colors match any chart style

### Label Display
*Clear, readable labels on the right side*

![Labels](screenshots/lite-labels.png)

> Shows IB levels and extension multiples

---

## 📥 Installation

### Prerequisites

- ✅ NinjaTrader 8 (version 8.0.0.0 or higher)
- ✅ Windows 10 or higher
- ✅ No license required (Free)

### Installation Steps

1. **Download the Indicator**

   Download `BadBuddha_IB_FibExtensions_Lite.zip` from:
   - [BadBuddha Customs](https://badbuddhacustoms.com)
   - [GitHub Releases](https://github.com/badbuddhatrades/BadBuddhaIBFibLite/releases)

2. **Import to NinjaTrader**

   ```
   1. Open NinjaTrader 8 Control Center
   2. Click Tools > Import > NinjaScript Add-On
   3. Browse to BadBuddha_IB_FibExtensions_Lite.zip
   4. Click Import
   5. Wait for "Import successful" message
   ```

3. **Compile (if needed)**

   ```
   1. Go to Tools > Edit NinjaScript > Indicator
   2. Find BadBuddha_IB_FibExtensions_Lite
   3. Press F5 to compile
   4. Verify "Compiled successfully"
   ```

4. **Add to Chart**

   ```
   1. Right-click any chart
   2. Select Indicators
   3. Find "BadBuddha_IB_FibExtensions_Lite"
   4. Click Add
   5. Configure settings (see below)
   ```

### Quick Start Settings

✅ **Default settings work great** for most day traders:
- IB Start: 09:30 (market open)
- IB Length: 60 minutes
- Anchor: Calendar Day
- Show all visual elements

---

## ⚙️ Configuration Guide

### Initial Balance Settings

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| **IB Length (minutes)** | int | 60 | Duration of Initial Balance period (1-360 min) |
| **Start Offset from Session Open (min)** | int | 0 | Minutes after session open (if not using fixed time) |
| **Use Fixed IB Start Time (HH:mm)** | bool | true | Use specific clock time vs. session offset |
| **IB Start Time (HH:mm)** | string | "09:30" | Clock time in 24-hour format |
| **Anchor IB to Calendar Day** | bool | true | `true` = Reset at midnight<br>`false` = Reset at session open |
| **Show IB Rectangle** | bool | true | Display shaded IB range box |
| **Show Midline (50%)** | bool | true | Display 50% equilibrium line |
| **Extend Lines To Session End** | bool | true | Extend to session end vs. current bar |

#### Examples

**ES Futures (Regular Hours)**
```ini
Start Time: 09:30
IB Length: 60 min
Anchor: Session (resets at 18:00)
```

**Forex EUR/USD (London Open)**
```ini
Start Time: 08:00
IB Length: 60 min
Anchor: Calendar Day (resets at midnight)
```

**NQ Futures (Overnight Session)**
```ini
Start Time: 18:00
IB Length: 30 min
Anchor: Session
```

### Style Settings

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| **Show Labels** | bool | true | Display text labels on right side |
| **Line Thickness** | int | 2 | Line width (1-10 pixels) |
| **IB Line Color** | Color | CornflowerBlue | IB High/Low line color |
| **Midline Color** | Color | CornflowerBlue | 50% midline color |
| **Ext Up Line Color** | Color | DarkOrange | Upward extension lines |
| **Ext Down Line Color** | Color | DarkOrange | Downward extension lines |
| **Rectangle Fill Color** | Color | SteelBlue | IB box fill color |
| **Rectangle Fill Opacity %** | int | 20 | Transparency (0-100%) |

### Update Settings

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| **Enable Update Check** | bool | true | Automatically check for updates |
| **Show Popup** | bool | true | Display update notification popup |

**Note**: Update checks occur every 7 days automatically

---

## 💡 Use Cases

### 1. **Day Trading - Session Range**

Use IB as a volatility gauge:

- ✅ Wide IB = High volatility day (trade breakouts)
- ✅ Narrow IB = Low volatility (potential expansion coming)
- ✅ Extensions = Profit targets for IB breakouts

### 2. **Support/Resistance Zones**

Fibonacci extensions act as key levels:

| Level | Usage |
|-------|-------|
| **0.5R** | First profit target or S/R flip |
| **1.0R** | Full range extension, strong level |
| **1.618R** | Golden ratio, major S/R |

### 3. **ICT/SMC Methodology**

Classic Initial Balance concepts:

- 📍 **IB High/Low** = Session liquidity levels
- 📊 **Extensions** = Premium/discount zones
- ⚖️ **50% Midline** = Equilibrium, fair value

### 4. **Trend Confirmation**

Track price action relative to IB:

```
Above IB High → Bullish bias (target upward extensions)
Below IB Low  → Bearish bias (target downward extensions)
Within IB     → Range-bound, wait for breakout
```

### 5. **Multi-Timeframe Analysis**

Combine with other timeframes:

- Daily chart: Identify larger IB range
- Intraday chart: Fine-tune entries at extension levels
- 5-min chart: See real-time interaction with levels

---

## 📊 Lite vs PRO Comparison

| Feature | Lite (Free) | PRO (Paid) |
|---------|-------------|------------|
| **IB Blocks per Day** | 1 | ✅ Up to 4 |
| **Fibonacci Levels** | 🔒 Fixed (0.5, 1.0, 1.618) | ✅ Fully customizable CSV |
| **Live Drawing During IB** | ❌ No | ✅ Yes (real-time updates) |
| **Font Customization** | 🔒 Arial, 12pt only | ✅ Any font, 8-32pt |
| **Line Styling** | Simple colors | ✅ Advanced (dash styles, gradients) |
| **Multi-Session Support** | ❌ Single IB only | ✅ Pre-market, Regular, After-hours, Overnight |
| **Color Customization** | ✅ Full | ✅ Full |
| **Rectangle Fill** | ✅ Yes | ✅ Advanced with opacity |
| **Session Anchoring** | ✅ Yes | ✅ Yes |
| **Update Frequency** | 7 days | 1 day |
| **Priority Support** | ❌ No | ✅ Yes |
| **License** | ✅ Free | NinjaTrader Vendor License |

### What You Get with PRO

Upgrade to PRO for:

1. ✅ **Multiple IB Sessions** - Track 4 IB blocks simultaneously
2. ✅ **Custom Fibonacci Levels** - Define any levels you want
3. ✅ **Live Drawing** - Watch IB form in real-time
4. ✅ **Advanced Styling** - Full Stroke editors like EMA
5. ✅ **Priority Support** - Direct vendor support

[Learn More About PRO](../Pro/README.md) | [Purchase PRO](https://badbuddhacustoms.com)

---

## 🎓 Tips & Best Practices

### Optimal Settings by Market

| Market | Start Time | IB Length | Anchor Mode |
|--------|-----------|-----------|-------------|
| **ES (Equity Futures)** | 09:30 | 60 min | Session |
| **NQ (Tech Futures)** | 09:30 | 30 min | Session |
| **EUR/USD (Forex)** | 08:00 | 60 min | Calendar Day |
| **BTC/USD (Crypto)** | 00:00 | 60 min | Calendar Day |
| **CL (Oil)** | 09:00 | 60 min | Session |

### Trading Strategies

**Strategy 1: IB Breakout**
```
1. Wait for IB to complete (e.g., 10:30)
2. Enter on break above IB High or below IB Low
3. Target: 1.0R or 1.618R extension
4. Stop: Opposite side of IB
```

**Strategy 2: Mean Reversion**
```
1. Price touches 1.618R extension
2. Look for rejection/reversal signals
3. Target: Return to IB 50% midline
4. Stop: Beyond 1.618R extension
```

**Strategy 3: Range Trading**
```
1. If price stays within IB for 2+ hours
2. Fade IB High and IB Low
3. Target: Opposite IB boundary or 50% midline
4. Stop: 0.5R extension beyond entry side
```

### Color Scheme Recommendations

**Dark Charts:**
```
IB Lines: Cyan or LightSkyBlue
Extensions Up: Lime or LightGreen
Extensions Down: OrangeRed or Salmon
Rectangle: DarkSlateGray (20% opacity)
```

**Light Charts:**
```
IB Lines: DarkBlue or Navy
Extensions Up: DarkGreen or ForestGreen
Extensions Down: DarkRed or Crimson
Rectangle: LightSteelBlue (15% opacity)
```

### Performance Tips

1. **Disable Rectangle** if you only need lines
   - Reduces drawing overhead
   - `Show IB Rectangle = false`

2. **Hide Labels** for cleaner chart
   - Use price scale to read levels
   - `Show Labels = false`

3. **Reduce Line Thickness** for minimal visual
   - `Line Thickness = 1`

---

## 🚀 Upgrade to PRO

### When to Upgrade

Consider PRO if you need:

✅ **Multiple Trading Sessions**
- Pre-market IB (04:00-09:30)
- Regular hours IB (09:30-16:00)
- After-hours IB (16:00-20:00)
- Overnight IB (20:00-04:00)

✅ **Custom Fibonacci Levels**
- Add your own proven levels (e.g., 0.382, 0.786, 2.618)
- Traditional Fibonacci ratios
- Market-specific extensions

✅ **Live Drawing**
- Watch IB form tick-by-tick
- Adjust trading decisions in real-time
- See range expansion as it happens

✅ **Advanced Styling**
- Dash patterns (dashed, dotted, etc.)
- Gradient fills
- Custom fonts (any installed font, 8-32pt)
- Professional stroke editors

### PRO Pricing & Purchase

- 💰 **One-time purchase** (no subscription)
- 🔄 **Free lifetime updates**

[View PRO Features](../Pro/README.md) | [Purchase PRO](https://badbuddhacustoms.com)

---

## 📞 Support & Updates

### Official Channels

- 🌐 **Website**: [https://badbuddhacustoms.com](https://badbuddhacustoms.com)
- 💬 **Support Email**: support@badbuddhacustoms.com
- 📖 **Documentation**: [GitHub Repository](https://github.com/badbuddhatrades/BadBuddhaIBFibLite)
- 🐛 **Bug Reports**: Submit via GitHub Issues

### Update Information

- 🔄 **Automatic Checks**: Every 7 days
- 📦 **Current Version**: v1.0.0.0
- 📅 **Release Date**: September 8, 2025
- 🔗 **Manifest URL**: Cloud-based update manifest

### Changelog

```
v1.0.0.0 (September 8, 2025)
  ✅ Initial release of BadBuddha IB Fib Extensions Lite
  ✅ Fixed Fibonacci levels: 0.5, 1.0, 1.618
  ✅ Full color customization
  ✅ Calendar day and session anchoring
  ✅ Automatic update checker (7-day cadence)
  ✅ IB rectangle with opacity control
  ✅ Clean label display
```

---

## 📝 Summary

**BadBuddha IB Fib Extensions Lite** is perfect for traders who want:

- ✅ **Free** - No cost, no license required
- ✅ **Simple** - Proven Fibonacci levels (0.5, 1.0, 1.618)
- ✅ **Clean** - Professional visualization
- ✅ **Flexible** - Session or calendar day anchoring
- ✅ **Customizable** - Full color control
- ✅ **Reliable** - Automatic update notifications

Perfect for:
- 📈 Beginning day traders learning IB concepts
- 💰 Traders on a budget
- 🎯 Those who prefer standard Fibonacci ratios
- 📊 ICT/SMC methodology practitioners
- 🔄 Traders testing before PRO upgrade

---

<div align="center">

### 🎁 It's Free!

**No credit card. No license key. Just download and trade.**

[Download Free Version](https://badbuddhacustoms.com) | [View PRO Features](../Pro/README.md) | [Report Issue](https://github.com/badbuddhatrades/BadBuddhaIBFibLite/issues)

---

**Made with ❤️ by BadBuddha Customs LLC** | *Empowering NinjaTrader 8 Traders Since 2024*

Copyright © 2025 BadBuddha Customs LLC | Free License

</div>
