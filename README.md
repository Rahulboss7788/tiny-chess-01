# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Rahulboss7788/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Rahulboss7788/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 4 KB original chess engine for the make.fun tiny-chess-01 bounty. 0x88 board, alpha-beta with iterative deepening, PVS, transposition table, killer moves, MVV-LVA ordering, null-move pruning, late-move reductions, quiescence search with check evasions — packed with LZMA into a single 3,839-byte main.py. No model calls, no network beyond the game env, deterministic.

v12 (round 4, fresh rebuild): fixed 90,000-node budget per move so a 1.6x slower grading host stays inside the 1,800 s trial wall — about 2.5 s a move on one CPU, max move well under the 10 s limit. Piece-list move generation and a signed value+PST table make it ~1.4x faster per node than the earlier v8. The v8 eval is kept (later eval additions were measured to cost Elo). Dead-drawn positions score 0 at once, and a clearly lost root prefers an immediate repetition draw. Perft-verified on six standard positions; practice trials run locally on the kit.

## Run it

```sh
MAKEFUN_ENV_URL=<env> python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=xt0p49wj&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
