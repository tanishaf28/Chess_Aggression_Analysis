# Chess_Aggression_Analysis
# ♟️ Does Aggression Win in Chess? 
Page Link: https://tanishaf28.github.io/Chess_Aggression_Analysis/chess.html


### A Data Science Analysis of 20,000+ Chess Games
**Codédex Data Science Monthly Challenge : February 2026**

---

## 🔬 Research Question

> *"Does aggressive chess play lead to more victories, or do patient, positional players have the advantage?"*

---

## 📁 Repository Structure
```
chess-aggression-analysis/
│
├── Chess.ipynb                          # Main analysis notebook (Google Colab)
├── chess_visualizations.py              # Standalone visualization scripts
├── Chess_Analysis_Presentation.pptx    # Slide deck (12 slides)
│
├── plots/
│   ├── win_rates_by_style.png
│   ├── crossover_point.png
│   ├── shocking_truth.png
│   ├── beginner_trap.png
│   ├── risk_vs_reward.png
│   ├── heatmaps.png
│   ├── violin_plots.png
│   └── ridge_plot.png
│
└── README.md
```

---

## 📊 The Dataset

| Property | Value |
|----------|-------|
| Source | [Lichess Chess Games — Kaggle](https://www.kaggle.com/datasets/datasnaek/chess) |
| Games | 20,058 |
| Time Period | 2016–2017 |
| Features | 16 columns (ratings, openings, moves, outcomes) |
| Missing Values | None — 100% complete |

### Opening Style Classification

| Style | Keywords Used |
|-------|--------------|
| **Very Aggressive** | Gambit, Attack, Sacrifice, Fried Liver |
| **Aggressive** | Sicilian, King's, Dutch, Alekhine, Dragon, Benoni |
| **Positional** | Defense, French, Caro, London, Queen's, Catalan |
| **Balanced** | Everything else |

---

## 🏆 Key Findings

### Finding 1 : Positional Play Edges Out Aggression

| Opening Style | White Win Rate | Black Win Rate | Draw Rate |
|---------------|---------------|----------------|-----------|
| Positional | **51.6%** | 43.7% | 4.7% |
| Very Aggressive | 50.7% | 44.6% | 4.7% |
| Aggressive | 47.2% | 47.8% | 5.1% |
| Balanced | 46.0% | **49.6%** | 4.4% |

> **Insight:** The total spread is only ~5.6%. Opening style has a surprisingly small effect on outcomes.

---

### Finding 2 — The Crossover Point (~1,650 Rating)

- **Below 1,650:** Aggressive openings win more. Opponents can't punish gambits correctly.
- **Above 1,650:** Positional play takes over. Experts accept gambits and convert the material advantage.

> **The Beginner Trap:** Aggression *feels* like it works at low levels because it does — but the wins come from opponent errors, not the opening's inherent strength.

---

### Finding 3 : The Shocking Truth: Skill >>> Style

| Factor | Win Rate Swing |
|--------|---------------|
| Opening style (best vs worst) | **~5.6%** |
| Rating gap (±400 points) | **~80%** |

Skill is roughly **14× more impactful** than opening choice.

| Rating Scenario | White Win Rate |
|-----------------|---------------|
| White 400+ ahead | ~85% |
| White 200+ ahead | ~68% |
| Roughly even | ~50% |
| Black 200+ ahead | ~32% |
| Black 400+ ahead | ~15% |

---

### Finding 4:  Aggressive Games Aren't Actually Shorter

| Style | Avg Turns |
|-------|-----------|
| Positional | 61.5 |
| Aggressive | 60.6 |
| Very Aggressive | 60.4 |
| Balanced | 56.8 |

> **Myth busted:** Gambits and attacks don't meaningfully shorten games. All styles cluster within a 5-turn range.

---

### Finding 5: Risk vs. Reward

- **Aggressive styles** → Higher variance. More upset potential. Better choice when you're the underdog.
- **Positional styles** → Lower variance. Results track skill more reliably. Better when you're the favorite.

---

## 📈 Visualizations

| # | Chart | Type | Key Insight |
|---|-------|------|-------------|
| 1 | Win Rates by Opening Style | Clustered Bar | Positional edges out at 51.6% |
| 2 | Aggression × Skill Level | Grouped Bar | Style effect varies by rating |
| 3 | The Crossover Point | Line Chart | Styles flip at ~1,650 rating |
| 4 | The Beginner Trap | Area Chart | Aggression advantage peaks ~1,100 |
| 5 | Skill vs Style Comparison | Side-by-side Bar | 5.6% vs 80% swing |
| 6 | Rating Gap Impact | Bar Chart | 14× more important than style |
| 7 | Decisiveness by Style | Horizontal Bar | Balanced games most decisive |
| 8 | Victory Type Breakdown | Stacked Bar | ~55% of all games end by resignation |
| 9 | Win Rate Heatmap | Heatmap | Rating gap dominates the color pattern |
| 10 | 3D Win Probability Surface | 3D Surface | Steep rating slope, flat length slope |
| 11 | Game Length Distributions | Violin Plots | Styles nearly identical in shape |
| 12 | Rating Ridge Plot | Ridge/KDE | Clean separation between skill bands |
| 13 | Risk vs. Reward | Bubble Chart | Aggressive = higher variance |

---

## 🚀 How to Run

### Option 1 : Google Colab (Recommended)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/YOUR_NOTEBOOK_LINK_HERE)

The notebook auto-downloads the dataset via `kagglehub` : no manual setup needed.

### Option 2 : Run Locally
```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/chess-aggression-analysis.git
cd chess-aggression-analysis

# Install dependencies
pip install pandas numpy matplotlib seaborn scipy kagglehub

# Run the notebook
jupyter notebook Chess.ipynb

# Or run visualizations standalone
python chess_visualizations.py
```

### Dependencies
```
pandas >= 2.0.0
numpy >= 1.24.0
matplotlib >= 3.7.0
seaborn >= 0.12.0
scipy >= 1.10.0
kagglehub >= 0.1.0
```

---

## 🎯 Conclusion

**Does aggression win in chess?**

**Sort of — but it's complicated.**

At lower skill levels, aggressive openings provide a genuine statistical edge. Gambits create chaos that weaker opponents can't handle. But as skill increases, positional play edges ahead gambits get accepted correctly, attacks get neutralized, and structural patience pays off.

The most important finding of all: **opening style accounts for at most a 5–6% difference in win rate. Your rating gap accounts for an 80% swing.**

> *"Play the style you love, then get really, really good."*

---

## 📦 Deliverables

| File | Description |
|------|-------------|
| `Chess.ipynb` | Full analysis notebook with all code, charts, and commentary |
| `chess_visualizations.py` | Standalone Python script for all 13 visualizations |
| `Chess_Analysis_Presentation.pptx` | 12-slide chess-themed presentation deck |

---

## 📚 Data Source

**Dataset:** [Chess Games : Kaggle (datasnaek)](https://www.kaggle.com/datasets/datasnaek/chess)
**Platform:** Lichess.org · **Period:** 2016–2017 · **License:** CC0 Public Domain

---

## 🏅 Challenge Submission

| Category | Approach |
|----------|----------|
| **Best Storyteller** | 9-chapter narrative arc from question → data → crossover → shocking truth → verdict |
| **Best Visualization** | 13 chart types including 3D surface, ridge plots, bubble charts, animated heatmaps |
| **Sherlock "Aha" Moment** | The 14× skill vs style finding — and the "beginner trap" crossover at 1,650 |

---

*Made with ♟️ and Python · Codédex Data Science Challenge · February 2026*
