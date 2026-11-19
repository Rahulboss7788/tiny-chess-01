# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Rahulboss7788/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Rahulboss7788/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 4 KB original chess engine for the make.fun tiny-chess-01 bounty. 0x88 board, alpha-beta with iterative deepening, transposition table, killer move, MVV-LVA ordering, null-move pruning, late-move reductions, quiescence search — packed with LZMA + base85 into a single 3,385-byte main.py. No model calls, no network beyond the game env, deterministic.

v11 (round 2, final): fixed 60,000-node budget per move (was 90,000) so a loaded grading host cannot trip the 1,800 s trial wall — practice trial-0: Elo 1,279, wall 555 s, max move 2.9 s, all pinned to one CPU. The v9 restored eval terms (passed-pawn bonus, bishop pair, endgame king PST, rook/queen PSTs) were measured to COST Elo on trial-0 (v9 90k: 1,279 vs v8 90k: 1,451), so they are reverted; the v8 eval is kept. Dead-drawn positions (insufficient material) score 0 at once, and a clearly lost root prefers an immediate repetition draw over grinding to the ply cap. Trial-0 verified on the submitted file: 1,279 (3W/3L), above the 1,154 floor.

## Run it

```sh
MAKEFUN_ENV_URL=<env> python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=xt0p49wj&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
