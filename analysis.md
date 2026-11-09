# PA1 Superfan: your analysis (TODO 11)

Write in your own words, wherever it says *your answer*.

## 1. How fast is each one?

`n` is the number of games. `p` is the number of players. Give the Big-O, and one sentence of why: what does the code actually do?

| Operation | Big-O | Why |
|---|---|---|
| `Roster.find` | O(1)| it looks up the name directly no loop |
| Finding a player in a plain list, one at a time | O(n) | it checks them one at a time worst case it looks through all|
| `GameLog.add_game` | O(1) | tail points to last node so just attatch at the end dont go through chain|
| `GameLog.games` | O(n)| goes through the entire chain head to tail once |
| `GameLog.last_game` | O(1)| returns self._tail.val automatically |
| `Season.record` | O(n)| games() is O(n) and then it loops over n games but O(n)+O(n) is O(n) |
| `Roster.leaderboard` | O(n log n) | sorting |

## 2. The Big-O race

Run `python3 race.py`, and paste your table here:

```
THE BIG-O RACE: find the last player, one lookup, in microseconds

   players    plain list      x    Roster.find      x
     2,000      144.7 us  start        0.52 us  start
     4,000      273.5 us   1.9x        0.60 us   1.2x
     8,000      656.1 us   2.4x        0.72 us   1.2x
    16,000     1054.6 us   1.6x        0.46 us   0.6x
```

**a)** Which column roughly doubles every round, and why?

the plain list column because it searches for last player which is the worst case the list has to check every other player before reaching that one

**b)** Why does the other column barely change?

its a dictionary lookup wo its always O(1) the work doesnt depend on how many players there are the small ups and dows are just timing it doesnt really grow

## 3. Your team

Which team, which season, and which websites did your numbers come from? Give the links.

## 3. Your team

My team is the Baltimore Ravens, and I used the 2025 NFL regular season
(17 games, finished 8–9). The stat I tracked for each player is touchdowns
scored (rushing + receiving).

- Game dates and scores:
  - https://profootballarchives.com/2025nflbal.html
  - https://www.espn.com.sg/nfl/team/schedule/_/name/bal
- Player touchdowns and games played:
  - https://www.statscrew.com/football/stats/t-BAL/y-2025
  - https://africa.espn.com/nfl/team/stats/_/name/bal/sort/completions
- Lamar Jackson's games played:
  - https://www.statmuse.com/nfl/ask/lamar-2025-passing
