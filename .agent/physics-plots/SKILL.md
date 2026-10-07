---
name: physics-plots
description: >-
  Create a single executable Python plotting script that displays figures with
  plt.show() using custom.mplstyle. Use when the user asks for plots only,
  matplotlib figures, quick visualization scripts, or a .py file to show plots
  without saving image files by default.
---

# Physics Plots

## When to use

Apply this skill when the user wants **plots only**: generate Python that draws a single plot or a set of plots. Do not turn the request into a larger analysis package unless asked.

## Goal

Put plotting code into a **single `.py` file**. The script may import local modules or load external data, but the deliverable is one executable entrypoint whose default behavior is to **show** figures, not save them.

## Required style

Always load the project matplotlib style:

```python
import matplotlib.pyplot as plt

plt.style.use("/path/to/custom.mplstyle")
```

Resolve `/path/to/custom.mplstyle` to the real path of `custom.mplstyle`:

1. Prefer an existing project file (commonly `python/custom.mplstyle` relative to the repo root, or an absolute path to that file).
2. If `custom.mplstyle` does not exist yet, **create it** in the same directory as the new `.py` script (or in `python/` if that is the natural home), using the template below, then point `plt.style.use(...)` at that file.
3. Pass a concrete filesystem path string to `plt.style.use` — not a bare style name.

### `custom.mplstyle` template (create only if missing)

```text
# custom.mplstyle
# Custom matplotlib style sheet
# Usage: plt.style.use('/path/to/custom.mplstyle')

#### TICKS ####
xtick.direction      : in
ytick.direction      : in
xtick.top             : True
xtick.bottom          : True
ytick.left            : True
ytick.right           : True
xtick.minor.visible   : False
ytick.minor.visible   : False
xtick.labelsize       : 20
ytick.labelsize       : 20

#### FONT ####
font.family            : serif
font.serif             : Computer Modern
text.usetex             : True

#### FONT SIZES ####
font.size             : 20
axes.labelsize        : 20
axes.titlesize        : 20
legend.fontsize        : 20

#### GRID ####
axes.grid             : True
axes.grid.which       : major
grid.color            : silver
grid.alpha            : 1.0
grid.linestyle        : --

#### LINES ####
lines.linewidth        : 2
axes.linewidth         : 1
xtick.major.width       : 1
xtick.minor.width       : 1
ytick.major.width       : 1
ytick.minor.width       : 1
```

## Default behavior

- **Do not** save plots by default (`savefig` only if the user explicitly asks).
- End with an interactive display call, typically `plt.show()`.
- One script → one figure or a small, related set of figures/subplots.
- Keep the script runnable: `python path/to/script.py`.
- Use r"...$...$..." for LaTeX in labels and titles.
- If multiple plot elements have to be shown with numerical content in labels, it is better to define a label array as
["label1", "label2", ...] and then use it in the plotting function, rather than using in-place string formatting in the label argument of the plotting function.

## Script pattern

```python
#!/usr/bin/env python3
"""Brief description of what is plotted."""

import numpy as np
import matplotlib.pyplot as plt

# Optional: import local helpers or load data
# from my_module import load_data
# data = np.loadtxt("data.csv", delimiter=",")

plt.style.use("/absolute/or/repo/relative/path/to/custom.mplstyle")

def main() -> None:
    # ... build data / curves ...
    fig, ax = plt.subplots()
    # ... ax.plot(...); labels; legend ...
    plt.show()

if __name__ == "__main__":
    main()
```

## Workflow

1. Clarify (briefly, only if needed) what to plot and where to put the `.py` file.
2. Ensure `custom.mplstyle` exists; create it if missing.
3. Write a single plotting script that uses that style path.
4. Default to `plt.show()`; omit `savefig` unless requested.
5. Prefer minimal dependencies (`numpy`, `matplotlib`); add others only when required for the plot.

## Anti-patterns

- Multiple unrelated scripts or a package layout for a simple plot request
- Saving PNGs/PDFs by default
- Using `plt.style.use("custom")` or another named style instead of the file path
- Large non-plotting analysis code unrelated to producing the figure(s)
