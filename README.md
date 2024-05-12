# poker-odds

A lightweight command line tool for calculating poker hand probabilities. No dependencies. No huge data files.

### API

The method used to calculate probabilities can be imported and used directly in a JS/node project:

```js
import { calculateEquity } from 'poker-odds'

const hands = [['AS', 'KH'], ['KD', 'QS']]
const board = ['TD', '7S', '8D']
const iterations = 100000 // optional
const exhaustive = false // optional

calculateEquity(hands, board, iterations, exhaustive)
```

`calculateEquity()` returns an array of hands with the results of the simulations:

```json
[
  {
    "hand": [
      "AC",
      "KH"
    ],
    "count": 990,
    "wins": 803,
    "ties": 15,
    "handChances": [
      { "name": "high card", "count": 376 },
      { "name": "one pair", "count": 479 },
      { "name": "two pair", "count": 78 },
      { "name": "three of a kind", "count": 13 },
      { "name": "straight", "count": 44 },
      { "name": "flush", "count": 0 },
      { "name": "full house", "count": 0 },
      { "name": "four of a kind", "count": 0 },
      { "name": "straight flush", "count": 0 },
      { "name": "royal flush", "count": 0 }
    ],
    "favourite": true
  },
  {
    "hand": [
      "KD",
      "QS"
    ],
    "count": 990,
    "wins": 172,
    "ties": 15,
    "handChances": [
      { "name": "high card", "count": 351 },
      { "name": "one pair", "count": 463 },
      { "name": "two pair", "count": 77 },
      { "name": "three of a kind", "count": 13 },
      { "name": "straight", "count": 41 },
      { "name": "flush", "count": 45 },
      { "name": "full house", "count": 0 },
      { "name": "four of a kind", "count": 0 },
      { "name": "straight flush", "count": 0 },
      { "name": "royal flush", "count": 0 }
    ],
    "favourite": false
  }
]
```
