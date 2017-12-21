An example of how we could implement terminal-like text rendering and blocks.

```python
# transform block position to real coordinates.
def get_coords(x, y, b_w = 16, b_h = 16):
    return (
        x * b_w,
        y * b_h
    )


# draw rectangle using block sizes.
def rect(x, y, w, h, colour = (255, 255, 255)):
    # maybe implement caching here.
    x, y = get_coords(x, y)
    w, h = get_coords(x + w, y + h)

    return draw_rect(x, y, w, h)


# draw a single block at x, y.
def block(x, y, colour = (255, 255, 255)):
    return rect(x, y, 1, 1)
```
