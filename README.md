# kalman-filter-oscillator

Javascript app to explore Kalman filter with a simple harmonic oscillator

## Vibe code prompts
https://g.co/gemini/share/a76d7e1d104e

Create a visualization of kalman filter updates. The visualization should show two probability distributions: the prior state, and the new measurement. The visualization should also show the underlying true state of the target. The true state of the target should be oscillating with a frequency controlled by the user. The state space for the filter should have position, velocity, and spring constant as unknowns. The measurements should be position only. There should be two buttons: new measurement, and run filter. When the new measurement button a probability distribution for the new measurement is displayed. When the run filter button is pressed the measurement distribution is not plotted, only the updated filter state. The target should continue to move in the background whether the buttons are pressed or not. That way the user can experience what it's like to collect sparse measurements

Could you flesh this out and create a javascript app to render the visualization and animation?

Use canvas

I don't see the state animation

Let's make the new measurement button the same as the run filter button. Change the text after each click to show the user the current state

I think the process noise is a bit too large. Could you give the user sliders to control various process noise values?

Ok now when the user presses the take measurement button lets freeze all animations. Then when the filter button is pressed we can resume animation

Now add an auto update that executes the measurement and filter steps at regular intervals controlled by the user. A "update-frequency" slider should control the rate of updates, going all the way down to zero. Also make the oscillator frequency go all the way to zero. Keep the user measure/filter button and still have it freeze time when take measurement is pressed. The auto update can reuse the same actions except shouldn't freeze time

Add a vertical line for the spring zero position. Use a different color for the state distribution it's black so I can't see the state very well. Make the state and measurement distributions both slightly transparent to visualize overlap. Increase the vertical height of the simulation window

The colors are still terrible. Could you totally revamp the visuals to give it a more modern look? Keep the same features but make it look prettier.

Remove the labels from the graph. It's obvious what the different components are. The simulation window is touching the measurement button. Bring the button and oscillator freq slider down a bit. Next to each slider show the current value. Finally bring the graphics down closer to the bottom of the canvas, and stretch the visualizations more vertically. Right now the bottom of the distribution is at about ~50% height on the canvas, and extends to ~80%. I want it to extend from ~20% to ~80%. Draw a solid horizontal line across the canvas at the bottom of the distribution as an axis

Ok one final button. Allow the user to toggle the spring constant estimation on and off. When off use the true constant from oscillator freq. When on estimate as we are doing now.

Instead of having the update transitions be a snap could you animate smoothly between the prior/post state during an update step?

Remove the "Estimate K" toggle button and add an "Enable Doppler" toggle button. When enabled the measurements include velocity data as well as position.
