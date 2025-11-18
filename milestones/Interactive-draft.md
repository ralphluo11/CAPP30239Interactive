# Democracy Trajectory Simulator

Jiahang Luo

## Goal

My goal remains the same as in the proposal: to build an interactive "Democracy Trajectory Simulator." The aim is to create a simulation-driven visualization that allows users to explore "what-if" scenarios for a country's democracy level over the next 10 years.

By allowing users to adjust factors like GDP growth, equality, and rule of law, the tool helps them see a plausible range of outcomes (as a fan chart). The ultimate goal is to help audiences connect economic and institutional assumptions to potential democratic trajectories. This has not changed.

## Data Challenges

My data challenges have shifted. I am now confident in my underlying data and model coefficients (data/coeffs.json). My main challenge is now methodological: how to accurately visualize the implications of this model.

The Visualization Method: My model (x_t = ρ·x_{t-1} + ... + ε_t) defines a complex probability distribution for the future. To visualize this, I am using a Monte Carlo method—running 1,000 random simulations and then drawing the quantiles (the 10-90% and 25-75% bands).

The "Accuracy" of the Simulation: My core challenge is this: Is this simulation method accurate?

The fan chart's shape is entirely dependent on these 1,000 paths. If I ran the simulation again, would the chart look slightly different? (It would, due to randomness). Is 1,000 paths the "right" number? Would 10,000 paths give a more "accurate" picture of the model's true probabilities? Would 100 paths be too few and too random?

Communicating the Method vs. the Model: I am confident in my model's coefficients, but I am uncertain how to justify or validate the simulation method that I'm using to present those coefficients to the user. The challenge is ensuring the visualization (the fan chart) is a faithful and stable representation of the underlying mathematical model.

## Walk Through

A user interaction starts when the page loads. The simulator immediately fetches the data and runs a default simulation.

1.  **Initial View:** The user sees the main fan chart, a set of controls (Country select, four sliders), and a legend at the bottom.
2.  **Controls:** The user can first select a **Country** from the dropdown menu. This sets the `start` value (the democracy index at "Now") for the simulation.
3.  **Simulation:** The user then adjusts the sliders for **"GDP growth"**, **"Equality change"**, **"Rule of law change"**, and **"Freedom of expression change"**.
4.  **Real-time Feedback:** As the user drags any slider (on an `input` event), the JavaScript instantly calls the `render()` function. This re-runs the `simulatePaths()` function (with 1,000 Monte Carlo paths) and recalculates the new quantiles (10-90% and 25-75%) and the median path.
5.  **Visualization Update:** The D3.js chart updates in real-time. The new quantile data is bound to the `.band90`, `.band50`, and `.median` paths, and the `d` attribute is redrawn. The user can visually see how their assumptions (e.g., increasing "Rule of law") cause the entire fan chart to trend upwards.


## Questions

1. Communicating the Model: I am currently showing the model's formula in the "How this prototype works" section. Given that I'm confident in the coeffs, is this the right way to show it?

2. Communicating the Simulation Method: How do I justify the Monte Carlo method to the user? Should I tell them, "The colored bands are the result of 1,000 random simulations"? Does this build trust (by showing the method is robust) or reduce it (by revealing it's an approximation, not a perfect mathematical calculation)?

3. Accuracy of the Simulation: How do I, the developer, validate that 1,000 paths is "accurate enough"? Is there a risk that the fan chart is misleading simply because the number of runs is too low?

4. Adding More Interactivity: Should I add a "comparison mode"? For example, allowing users to "lock" one simulation's results ("high growth") and then overlay a second simulation ("low growth") or two countries projection to see the difference clearly.

5. Visual Polish & Animation: Is it possible (and desirable) to implement more advanced animations and visual effects, similar to the smooth, narrative-driven scrolling and transitions seen on Apple's website? Would this help the user experience, or would it be distracting?
