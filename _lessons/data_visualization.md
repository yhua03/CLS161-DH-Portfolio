---
layout: page
title: Visualizing Data with Bokeh and Pandas
description: This lesson uses Python to visualize and present data using the Bokeh and Pandas libraries.
---

## Source
[Harper, C. (2018). Visualizing data with Bokeh and Pandas. _The Programming Historian_, 7. https://doi.org/10.46430/phen0081](https://programminghistorian.org/en/lessons/visualizing-with-bokeh)

## Reflection
TODO

## Code

## The Basics of Bokeh
Before getting into visualizing the entire data set, we will first look at the 
basics of the bokeh Python library.
```python
# my_first_plot.py
from bokeh.plotting import figure, output_file, show
output_file('my_first_graph.html')

x = [1, 3, 5, 7]
y = [2, 4, 6, 8]

p = figure()

p.circle(x, y, size=10, color='red', legend='circle')
p.line(x, y, color='blue', legend='line')
p.triangle(y, x, color='gold', size=10, legend='triangle')

p.legend.click_policy='hide'
show(p)
```

<img src="../assets/first_plot.png" alt="drawing" width="450"/>