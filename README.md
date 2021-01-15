# glider-panel-demo
Demo of how to use holoviz to visualize gliderdata

Launch interactive Panel App with MyBinder.org:

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/dhruvbalwada/glider-panel-demo/main?urlpath=%2Fpanel%2Fholoviz_gliderdash)


Launch Jupyter Lab Interface:

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/dhruvbalwada/glider-panel-demo/main?urlpath=lab)


Run locally (note, can take a few minutes for code app to appear due to data loading)
```
git clone https://github.com/dhruvbalwada/glider-panel-demo.git
cd glider-panel-demo 
conda env create -f binder/environment.yml
conda activate gliderviz 
panel serve holoviz_gliderdash.ipynb
# or launch jupyter lab to edit the app with `jupyter lab`
```
