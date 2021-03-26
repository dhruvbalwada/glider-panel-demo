# glider-panel-demo
This repository showcases how [Holoviz](https://holoviz.org/) libraries can be used to build a dashboard to easily visualize [ocean glider](https://en.wikipedia.org/wiki/Underwater_glider) data. The scales of ocean observed by gliders are extremely dynamic and contain variability over a large range of scales, hence the interactive visualization process really helps to make faster discovery in the data.   
  
To see the final dashboard launch the interactive Panel App with MyBinder.org:  

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/dhruvbalwada/glider-panel-demo/main?urlpath=%2Fpanel%2Fglider_combined_plot) 

This should being up a running version of the dashboard, and relies on the notebook `glider_combined_plot.ipynb` (the main notebook in this repo).  

For interacting with all the notebooks in this repo Launch Jupyter Lab Interface:  

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/dhruvbalwada/glider-panel-demo/main?urlpath=lab) 

The other notebooks contain code on how to preprocess the data before it is ready for use in the dashboard, and also contains code that are used to build the individual components of the dashboard (a lat-lon plot and a glider section plot).  

Binder might not provide a very smooth interaction with the dashboard since it runs remotely and is resource limited. Smoother interaction is possible by running the dashboard ony your local machine. To run locally:
```
git clone https://github.com/dhruvbalwada/glider-panel-demo.git
cd glider-panel-demo 
conda env create -f binder/environment.yml
conda activate gliderviz 
panel serve holoviz_gliderdash.ipynb
# or launch jupyter lab to edit the app with `jupyter lab`
```

Here is a wishlist of things we would like to see happen in the future:

- A smoothly working 2 way link between the time slider and panning/zooming glider figure. Currently the glider section can only be panned using the sliders, it would be nice if the sliders responded to paning using the tools that are attached to the plot.
- Have a second x axis with the alternate dimension (time or distance) (Solved here, but needs a bit more of JS background: https://discourse.holoviz.org/t/secondary-x-axis/1965/7)
- Right now zooming and adjusting time slider resets different panels, would be nice to keep zoom levels.
- Similarly, the colorlevels (selected using the attached hist) are reset when adjusting sliders. Would be nice to stop this reseting.
- Make sure that the entire plot is only replotted when needed, to ensure a smooth interaction. Currently this is working for the trajectory plot, but there was some trouble trying to do it for the glider section. In particular it was unclear how to set xlim in a separate function than the plotting function/passing dynamic map to dynamic map. (https://discourse.holoviz.org/t/how-to-set-fine-grained-dependencies-when-setting-options-in-the-viewable-function/2012)
- Improve documentation in notebooks and scripts so that other users with their own data sets can easily incorporate their own data sets into it.
- Have an interactive 3D version for the glider section (https://docs.pyvista.org/examples/00-load/create-surface-draped.html#sphx-glr-examples-00-load-create-surface-draped-py).
- Direct access to data sets from online data repositories. Currently the SSH, FSLE or glider fields being plotted have to be manually downloaded and manipulated before they are put into the dashboard. It would be nice if some of these fields be automatically accessed, rather than having to manually download them first.
- Have a way to save state, so that when returning to the dashboard the exact options as a previous session can be loaded. Or the dashboard state can be shared with others. 
