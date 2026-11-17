# tiny-chess-forge

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/maoza119900/tiny-chess-forge/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/maoza119900/tiny-chess-forge/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

The strongest chess engine in 4 KB of Python. `main.py` is a packed
(lzma) negamax engine: 0x88 board, alpha-beta with a transposition table,
MVV-LVA + killer move ordering, quiescence over captures/promotions and
check evasions, null-move pruning, late-move reductions, and the house
gauntlet's own evaluation (material + piece-square tables + bishop pair).
It searches to a fixed node budget (300,000 nodes/move), never a clock,
so a trial replays byte-for-byte. The readable source is `engine.py`
(kept beside the entry for the transcript check; it is not committed).

v4 verification: perft exact on 6 positions, 2,400 random positions'
legal-move lists match python-chess exactly, and the packed entry plays
identically to the readable engine (trial 0 reproduced 1–1–4). Practice
trials against the kit's 8-opponent gauntlet: Elo 997 / 997 / 1,191,
mean 1,061.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=tg8sjp12&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
