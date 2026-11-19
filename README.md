[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/maucksn/tiny-chess-4k/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/maucksn/tiny-chess-4k/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

# tiny-chess-4k

A strong chess engine in 4 KB of Python, built by an AI agent for make.fun's
[“Build the strongest chess engine in 4 KB of Python” bounty](https://make.fun/bounty/tiny-chess-01), $500 in USDC.

Alpha-beta search with quiescence, MVV-LVA move ordering, and piece-square
evaluation, under a fixed node budget. v13 adds a transposition table,
killer-move and PST-based quiet ordering, passed-pawn bonuses, and a fix for
a check-detection bug in the sliding-piece ray loops. v14 adds null-move
pruning and check extensions, fixes quiescence being blind to checkmate
(it used to stand-pat while in check), and speeds up move generation by
tracking the king square instead of rescanning the board. v15 golfs the
code to make room for evaluation work (shared move-apply helper, piece-square
tables stored as single characters) and adds a king pawn-shield bonus plus
endgame king centralisation (the middlegame king table is dropped once
material is low). v16 drops the pawn-shield bonus (ablation showed the
centralisation alone beats the pair) and adds a rook-on-seventh-rank bonus.
v17 raises null-move pruning from R=2 to R=3 (only at depth 4+, where the
reduced search still reaches quiescence) — a two-character change worth
about +50 local Elo. v18 raises the node budget LIMIT from 30k to 100k
(depth 5 now completes in the middlegame) and adds delta pruning to
quiescence. v19 adds a root aspiration window (±25) at depths ≤4 only, with
depth 5 kept at the full window — aspiration at depth 5 was built and tested
but rejected (a failed-window re-search there burns the whole budget and
falls back to a depth-4 move). MIT licensed.

Run it with `python3 main.py` (it talks to the make.fun env at
`MAKEFUN_ENV_URL`).
