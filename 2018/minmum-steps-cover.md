# Minimum steps needed to cover a sequence of points on an infinite grid

ou are in an infinite 2D grid where you can move in any of the 8 directions:
(x,y) to (x+1, y), (x - 1, y), (x, y+1), (x, y-1), (x-1, y-1), (x+1,y+1), (x-1,y+1), (x+1,y-1) You are given a sequence of points and the order in which you need to cover the points. Give the minimum number of steps in which you can achieve it. You start from the first point.
Example:

Input: [(0, 0), (1, 1), (1, 2)] Output: 2 It takes 1 step to move from (0, 0) to (1, 1). It takes one more step to move from (1, 1) to (1, 2).

## Approach

One way to reach from a point (x1, y1) to (x2, y2) is to move abs(x2-x1) steps in the horizontal direction and abs(y2-y1) steps in the vertical direction, but this is not the shortest path to reach (x2, y2). The best way would be to cover the maximum possible distance in a diagonal direction and remaining in horizontal or vertical direction.

## Code

```python
def find_min_steps(p1, p2):
    dx = abs(p1[0] - p2[0])
    dy = abs(p1[1] - p2[1])
    return max(dx, dy)

def min_cover_steps(inputs):
    step_count = 0
    for i in range(len(inputs) - 1):
        step_count += find_min_steps(inputs[i], inputs[i + 1])
    return step_count
```

## Reference

[Minimum steps needed to cover a sequence of points on an infinite grid](https://www.geeksforgeeks.org/minimum-steps-needed-to-cover-a-sequence-of-points-on-an-infinite-grid/)