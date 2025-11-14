---
title: Coding Camp
nav_order: -4
math: true
toc: true
has_toc: false
---

# Noob Coder Ascension Plan

---

Starting from Oct 26,

- All systematic learning, see [`./csdiy`](./csdiy)
- Documents
  1. Writing style
      - [x] [PEP 8](https://peps.python.org/pep-0008/)
      - [ ] [Google python style guide](https://google.github.io/styleguide/pyguide.html)
  2. [Version control and git](https://swcarpentry.github.io/git-novice/)
  3. Project development
      - [x] [uv](https://docs.astral.sh/uv/guides/projects/)
      - [ ] [ruff](https://docs.astral.sh/ruff/)
      - [ ] [Scientific Python Library Development Guide](https://learn.scientific-python.org/development/)
      - [ ] [Python Packaging User Guide](https://packaging.python.org/en/latest/)
- Practical tools
  - [`./aws/cloud`](https://skillbuilder.aws/learn)
- Hands-on projects
  - FINM 325 Assignments (Backtesting Framework): [`./backtest`](./backtest) 🌟🌟🌟🌟
  - Exchange Simulator / Matching Engine: [`./simulator`](./simulator) 🌟🌟🌟🌟🌟
  - Market Data Pipeline: [`./data_pipeline`](./data_pipeline) 🌟🌟🌟🌟🌟
  - Rewrite resume projects
    - ~~Infinity capital~~
    - DolphinDB (rewrite with python) 🌟🌟🌟
- Other references
  - [`./roadmap`](https://roadmap.sh/backend)

[Quantlib](https://github.com/lballabio/QuantLib) is a great resource, however it's written in C++. Definitely won't work on it before capturing the basics of C++. References for future use: [Implementing quantlib](/pdf/implementingquantlib.pdf), [Quantlib-python Cookbook](/pdf/quantlibpythoncookbook.pdf).

---

*Updated (Oct 25)*: Now I decided to break into quant dev, so I adjusted my course plan. I gave up the concentration on "Rates and Credits", changing into "Financial Computing". So now my concentrations are "Options and Derivatives" and "Financial Computing". Winter 2025 would be very tough, but once I make it and if I'm still alive, I would be unstoppable. I admit that UCSD's DSA micromaster is not a great resource to learn. Neetcode should be better (I invested \$120).

---

*Updated (Oct 26)*: Suggestion from Claude. **Quality > Quantity.** Recruiters spend 30 seconds on your GitHub. Better to have:

- 2-3 excellent projects with great documentation
- Than 10 mediocre repos

Your DDB experience is unique. If you build that one project really well, document it clearly, and can talk about it confidently in interviews, that alone can carry your resume.

---

*Updated (Nov 3)*: After showing Claude some JDs for QuantDev, it removed one project: Kaggle's Hull Tactical, and lower the importance of DDB's portfolio optimizer rewrite. Now, the most useful projects for job search are the followings:

- Exchange Simulator / Matching Engine
  - Fits well for CS61B and DSA in general
  - Good documentations
  - Have github repo in Java
- Backtesting Framework
  - Extends on FINM 325's homeworks
  - Good documentations
  - Try achieve industry-grade performance in Python
- Market Data Pipeline
  - Mentions a lot in JDs
  - Practice system design