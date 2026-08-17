# AI Recommendation & the Disposition Effect in Portfolio Management

![Method](https://img.shields.io/badge/Method-Framed%20Field%20Experiment-1f6feb)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Focus](https://img.shields.io/badge/Focus-Behavioral%20Finance-blue)

Course: Experimental Economics, University of Pittsburgh

## Does a Real-Time AI Sell Recommendation Reduce the Disposition Effect?

**Key takeaway:**
A **research proposal** (a pre-registration-style design, not a completed study) for a framed field experiment testing whether an in-the-moment AI sell recommendation reduces the **disposition effect** in finance-trained subjects. The design isolates the treatment using a controlled, between-subjects portfolio simulation with pre-programmed price paths held identical across both arms, so behavioral differences are attributable to the recommendation alone. The primary outcome is **PGR minus PLR** (the proportion of gaining positions realized minus the proportion of losing positions realized). Figure 1 in the paper is **simulated for illustration**, showing what a successful result would look like, not data collected from participants.

---

## Role & Methods
**Role:** Co-author, experimental design and empirical strategy
**Design:** Framed field experiment (Harrison and List, 2004), between-subjects randomized design
**Outcome & inference:** PGR minus PLR, one-sided two-sample t-test, OLS with controls, override-rate analysis
**Proposed platform:** oTree (open-source experimental economics platform)

---

## Research Question
Does receiving a real-time AI sell recommendation during an incentivized portfolio management task reduce the magnitude of the disposition effect, measured as the difference between the proportion of gains realized and the proportion of losses realized, in participants with finance training, compared to those who receive no AI recommendation?

---

## Motivation & Contribution
The disposition effect (selling winners too early, holding losers too long) is well documented and survives professional training. Prior debiasing work relied on pre-task warnings that shape the mindset before a decision forms. The untested case is an in-the-moment recommendation that has to compete with an active emotional response, delivered in a human-in-the-loop setting where a person receives AI guidance and still decides whether to act. That setting is now the dominant real-world configuration across institutional and retail investing, not a hypothetical.

The proposal also states a mechanism for why the intervention could work where training does not. The disposition effect is reference-dependent: it needs a purchase price to anchor to and the felt pain of realizing a loss. A recommender built on price momentum and pattern recognition carries neither, so it can issue the sell signal a loss-averse human suppresses.

---

## Proposed Design
- **Task:** manage a simulated portfolio of 8 stocks over 10 rounds, with buy, sell, or hold decisions each round.
- **Price paths:** pre-programmed from historical equity volatility parameters, held identical across conditions.
- **Treatment:** in the AI condition a banner recommends a SELL each round; the no-AI condition is identical with no banner.
- **AI accuracy:** recommendations are correct about 70% of the time, realistic and enough to prevent subjects from simply following an always-right tool.
- **Sample:** about 180 finance-trained participants, 90 per condition, powered to detect a medium effect (Cohen's d about 0.5) at 80% power.
- **Incentives:** tournament pay on relative performance, chosen over trade earnings to avoid rewarding subjects for mechanically obeying the tool.
- **Integrity:** random assignment, a cover story, a post-task manipulation check, and IRB review of the mild deception.

---

## Proposed Analysis
- **Primary:** one-sided two-sample t-test comparing mean PGR minus PLR between conditions (p less than 0.05).
- **Secondary:** OLS of PGR minus PLR on the AI indicator with controls for financial literacy, years of finance training, and self-reported AI familiarity.
- **Mechanism:** override rates computed separately for losing and winning recommendations; higher override on losers would show loss aversion persisting even with explicit AI guidance to sell.
- **Success criterion:** a statistically significantly lower PGR minus PLR in the AI condition, with lower loss-side override rates than in the no-AI condition.

---

## Repository Contents

### Report
- **Proposal (PDF):**
  [Experimental_Econ_Research_Proposal.pdf](Experimental_Econ_Research_Proposal.pdf)
  *(GitHub previews PDFs in the browser. If it does not load, use the **Download** button to view locally.)*

---

## Notes
This is a research design, not an executed study, so there is no collected dataset or estimation output. The proposed implementation is in oTree and the full analysis plan is specified in Section IV of the paper. A working oTree implementation, or a simulation of the design under varying AI accuracy, could be added later to turn the proposal into a runnable study.

---

**[← Back to Applied Data Analysis & Econometrics](../README.md)**
