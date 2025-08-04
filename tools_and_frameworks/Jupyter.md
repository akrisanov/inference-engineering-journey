> A notebook is a document made of cells. You can write in some of them (markdown cells) or you can perform calculations in Python (code cells) and run them.

## Modes

You can switch back and forth between `Command Mode` and `Edit Mode` with <kbd>Esc</kbd> and <kbd>Enter</kbd>.

## Shortcuts

- `b` – Create new cell underneath the current one
- `m` – Convert cell to Markdown
- `y` – Convert cell to Code
- `d` + `d` – Delete cell
- `Shift+Enter` – Run the code or markdown on a cell
- `Up Arrow` / `Down Arrow` – Toggle across cells
- `Shift`+`Arrow up`/`Arrow down` – Select multiple cells
- `Shift+M` – Merge selected cells
- `0+0` – Reset Kernel

## Cell Tricks

- `?function-name` – Show the definition and docstring for that function
- `??function-name` – Show the source code for that function
- `Shift+Tab` (press once) – See which parameters to pass to a function
- `Shift+Tab (press three times)` – Get additional information on the method

## Code Cell

Type `!` before you shell command.

## Line Magics

```python
%matplotlib inline
%timeit
%debug
```

## Useful Extensions

- [RISE](https://rise.readthedocs.io/en/latest/) – Jupyter Slideshow Extension
- [fastpages](https://github.com/fastai/fastpages) – Writing a blog in Jupyter
- [nbdev](https://nbdev.fast.ai/getting_started.html) – a notebook-driven development platform