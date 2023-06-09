This module calculates probabilities for dice equations, provided in the form of a string (e.g., "3d6 + 5"), using [Icepool](https://github.com/HighDiceRoller/icepool). This is still very much a work in progress.

[Icepool](https://github.com/HighDiceRoller/icepool) is an incredibly powerful and flexible tool for calculating probabilities for game mechanics that use dice to determine the outcome. However, dice equations are written out in code rather than as a string. For example, the equation "3d6 + 5" gets represented as `3 @ d(6) + 5`. This makes applying Icepool to dice equations taken from text files rather difficult, which is what this module aims to solve.

# Example

```python
from dice_roller import *
import matplotlib.pyplot as plt

d = Dice_Roller('3d6 + 5')

fig, ax = plt.subplots()
ax.plot(d.value.outcomes(), d.value.probabilities())
ax.set_xlabel('value')
ax.set_ylabel('probability')
plt.show()
```

![probability distribution example](https://github.com/tomedunn/dice_roller/blob/master/assets/images/example-distribution.png?raw=true)