# glider-panel-demo
This repository showcases how [Holoviz](https://holoviz.org/) libraries can be used to build a dashboard to easily visualize [ocean glider](https://en.wikipedia.org/wiki/Underwater_glider) data. The scales of ocean observed by gliders are extremely dynamic and contain variability over a large range of scales, hence the interactive visualization process really helps to make faster discovery in the data.   
  
To see the final dashboard launch the interactive Panel App with MyBinder.org:  

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/dhruvbalwada/glider-panel-demo/main?urlpath=%2Fpanel%2Fglider_combined_plot) 

This should being up a running version of the dashboard, and relies on the notebook `glider_combined_plot.ipynb`.  

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
