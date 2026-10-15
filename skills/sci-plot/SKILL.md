---
name: sci-plot
description: House style for scientific matplotlib figures. Use whenever writing or changing code that draws a plot, histogram or figure.
---

# Scientific plots

Every figure answers one question; write that question as a comment above the plotting code.

1. One script per figure or topic in `scripts/`. It saves `figures/<name>.png` (dpi 200) and `figures/<name>.pdf`, then closes the figure. Never call `plt.show()`.
2. Simulation in blue `#1F77B4`, exact formula in red `#D62728`, reference lines grey dashed. Overlay the formula on every simulation that has one.
3. Label every axis with the quantity in words. Put the sample size in the legend.
4. Use a log axis when values span more than two decades. Zeros cannot sit on a log axis: drop them and draw a line at 1/(number of samples).
5. Panels that are compared share their x-axis.
6. Seed once at the top (`rng = np.random.default_rng(<seed>)`) and pass `rng` to every sampler.
7. After saving, open the PNG and check it at the size it will be shown: no text below 7.5 pt, no text on a curve or a point, the formula on the simulation. Then tell me in one sentence what the figure shows.
8. Draw the figure at the size it will be shown and never scale it afterwards. For slides: about 2.5 x 2 in for half the width, 5 x 2.2 in for the full width. At that size no text is smaller than 7.5 pt, legends included.
9. Keep text off the data. Put legends and labels in empty space or outside the axes; if a legend covers points or a curve, move it or shorten its labels and put the details in the caption.
