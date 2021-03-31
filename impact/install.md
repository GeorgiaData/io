
# Industry ML - Websocket Setup

Source:   

[Final\_submission/data\_viz/national\_choropleth](https://github.com/modelearth/industries/tree/master/Final_submission/io/impact)  


## Necessary Software

- Ran on Python 3.7.6

Python libraries - Install with: <code>python3 -m pip install [library]</code>  
- [sklearn] v. 0.22.1
- [websockets] v. 8.1
- [asyncio] v. 3.4.3
- [numpy] v. 1.18.1
- [cffi]
- [cryptography]
- [pandas] v. 0.25.3


To run the following, commented out <code>export PIP_REQUIRE_VIRTUALENV=true</code> momentarily in .zshrc
python3 -m pip install websockets
python3 -m pip install numpy
python3 -m pip install sklearn
python3 -m pip install joblib  


## Install Instructions

### CREATE THE MODEL

You can skip creating the model since the model data is already built within this repo.  

Go to your webroot and run <code>jupyter notebook</code>  

If not found, first install [Anaconda using Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)

Need to confirm this is the one to run:  
Open Final_submission/Regression\_Final\_model.ipynb and run all cells.   

<!--
Bug: Running #19 is returning:  
<blockquote>
/Users/[username]/opt/anaconda3/lib/python3.7/site-packages/sklearn/linear_model/_coordinate_descent.py:1790: ConvergenceWarning: Objective did not converge. You might want to increase the number of iterations. Duality gap: 89971568.4297196, tolerance: 580758.9170684905 check_random_state(self.random_state), random)<br><br>

/Users/[username]/opt/anaconda3/lib/python3.7/site-packages/sklearn/base.py:434: FutureWarning: The default value of multioutput (not exposed in score method) will change from 'variance_weighted' to 'uniform_average' in 0.23 to keep consistent with 'metrics.r2_score'. To specify the default value manually and avoid the warning, please either call 'metrics.r2_score' directly or make a custom scorer with 'metrics.make_scorer' (the built-in scorer 'r2' uses multioutput='uniform_average').
  "multioutput='uniform_average').", FutureWarning)
</blockquote>
-->


### RUN THE MODEL

Optional: Open console in root directory and run:
    
    cd io/impact
    python3 -m http.server 8000


Open new console at root directory and run:

    cd io/impact/src

Now start to the websocket server. 
(Allows red bars to indicate predictions in lower right bar graph.)

    python3 server.py

You can ignore the joblib error. 


## View Website

- Open web browser and go to: 
    - [http://localhost:8000/](http://localhost:8000/) 

- Also works as a subfolder.


    - [http://localhost:8887/io/impact/](http://localhost:8887/io/impact/)  

If the websocket server did not start, view websocket-notes.md.  

- Choose a county (Fulton County, GA is selected by default) and adjust the sliders to predict 
      what effects a larger or smaller industry plays in cancer rates for that county.

- Hit the 'Update Prediction' button for each new prediction.


## Includes Library

[Range.js](https://niandco.github.io/range/) is a lightweight pure JavaScript plugin 


## Changes

#from sklearn.externals import joblib  
import joblib  
Based on [stackoverflow](https://stackoverflow.com/questions/61893719/importerror-cannot-import-name-joblib-from-sklearn-externals)  


    

