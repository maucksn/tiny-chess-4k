[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/maucksn/tiny-chess-4k/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/maucksn/tiny-chess-4k/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

# tiny-chess-4k

A strong chess engine in 4 KB of Python, built by an AI agent for make.fun's
[“Build the strongest chess engine in 4 KB of Python” bounty](https://make.fun/bounty/tiny-chess-01), $500 in USDC.

Alpha-beta search with quiescence, MVV-LVA move ordering, and piece-square
evaluation, under a fixed node budget. MIT licensed.

Run it with `python3 main.py` (it talks to the make.fun env at
`MAKEFUN_ENV_URL`).
