# ☕ BUZZZ 

> **A caffeine intelligence engine.**

BUZZZ is a single-file, zero-backend web app that models caffeine pharmacokinetics in real time. Input your body metrics and coffee consumption, and BUZZZ maps exactly how much caffeine is running through your system — hour by hour, for 24 hours.

---

## ✨ Features

### 🧬 Metabolic Profile
- Calculates your **Basal Metabolic Rate (BMR)** using the **Mifflin-St Jeor equation**
- Supports male, female, and other gender inputs
- Validates age (1–120), weight (1–500 kg), height (1–300 cm)

### ☕ Coffee Logger
- **12 coffee types** with exact caffeine values per size (Small / Regular / Large)
- **Unlimited entries** up to a cap of 20 (DoS protection)
- Time picker per entry — log drinks at different hours
- Instant caffeine dose badge per entry

**Supported drinks:**
| Type | Small | Regular | Large |
|---|---|---|---|
| Drip/Brewed Coffee | 130mg | 195mg | 260mg |
| Americano | 69mg | 104mg | 138mg |
| Cold Brew | 129mg | 194mg | 259mg |
| French Press | 100mg | 150mg | 200mg |
| Decaf Coffee | 4mg | 5mg | 7mg |
| Instant Coffee | 69mg | 104mg | 139mg |
| Cappuccino / Latte | 71mg | 107mg | 142mg |
| Flat White | 130mg | 195mg | 260mg |
| Nitro Cold Brew | 143mg | 215mg | 287mg |
| Iced Coffee | 80mg | 120mg | 160mg |
| Vietnamese Coffee | 200mg | 300mg | 400mg |
| Espresso (Single Shot) | — | 69mg | — |

### 🧠 Pharmacokinetics Engine
- Uses **first-order exponential decay** (pharmacokinetic superposition)
- Formula: `Remaining = Dose × (0.5)^(elapsed / half-life)`
- Supports **multiple simultaneous doses** via superposition
- Adjustable **half-life slider: 3–7 hours** (default 5h population average)
- Simulates caffeine concentration at **0.1-hour resolution** for 24 hours

### 📊 Output & Visualisation
- **Animated 24-hour decay curve** (Chart.js) with 200mg and 50mg threshold lines
- **Hour-by-hour breakdown** — scrollable bar chart, auto-scrolls to first active hour
- **Peak caffeine time** and **peak mg** — derived independently for chart and timeline
- **Milestone times** — when you drop below 200mg / 100mg / 50mg / near zero
- **"Can You Sleep?" indicator** — checks caffeine at 11 PM against 50mg threshold

### 🎯 Buzz Score & Personality
- **Buzz Score (0–100):** `peak caffeine / 400mg × 100` — animated ring counter
- **5 Roast Personalities:**
  - 🧊 Calm Strategist — low intake, measured
  - ⚡ Functional Human — moderate, holding it together
  - 🔥 Chaos Architect — high intake, peak >350mg
  - 💀 Sleep Is A Myth — Vietnamese coffee detected
  - 😐 Pretending To Participate — decaf only

---

## 🎨 Design

**Aesthetic:** Y2K Hyperpop Terminal — acid green on pitch black, glitch animations, scanline overlay, noise grain texture.

**Typography:**
- `Black Ops One` — display headings
- `Bebas Neue` — section labels, buttons
- `Space Mono` — body, data, monospace UI
- `VT323` — terminal labels, microcopy

**Colour palette:**
```
--acid:   #b8ff00  (primary green)
--acid2:  #00ffb3  (teal accent)
--hot:    #ff2d6b  (alert/danger)
--orange: #ff6b00  (warning)
--bg:     #030303  (near-black)
```

**Effects:** Custom phosphor cursor, steam animation, glitch logo loop, marquee ticker, glassmorphism cards, entry-pop animations, jitter hover states.

---

## 📱 Responsive Breakpoints

| Breakpoint | Target |
|---|---|
| `≤768px` | Tablet — tighter grids, smaller chart |
| `≤600px` | Large phone — single column, 16px inputs (prevents iOS zoom), sticky CTA |
| `≤390px` | iPhone SE / Galaxy A — condensed stats, smaller buzz ring |
| `≤320px` | Galaxy Fold / older phones — ultra-compact layout |
| Landscape mobile | Hero collapses, scroll hint hidden |
| `hover: none` | Hover effects disabled, cursor hidden, touch-optimised interactions |

---

## 🛠 Tech Stack

| Dependency | Version | Purpose |
|---|---|---|
| **Chart.js** | 4.4.1 | Caffeine decay curve visualisation |
| **Google Fonts** | — | Black Ops One, Space Mono, Bebas Neue, VT323 |

Everything else is **vanilla HTML, CSS, and JavaScript** — no framework, no bundler, no build step.


---

## ⚠️ Disclaimer

BUZZZ is designed for **educational purposes only**. Visualisations are based on publicly available data about caffeine metabolism. Individual responses to caffeine vary significantly based on genetics, medications, tolerance, and other factors. This tool should not be used for medical decisions. Always consult a healthcare professional for medical advice.
