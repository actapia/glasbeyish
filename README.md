# glasbeyish

This is a library that implements a method described in the paper "Colour
Displays for Categorical Images" by Glasbey et al. for finding optimal distinct
color palettes of a specified size.

Unlike the [glasbey](https://github.com/lmcinnes/glasbey) library, this library
implements the simulated annealing method described in the paper rather, than
the iterative method. The simulated annealing method can often give better color
palettes at the expense of longer run times.

## Examples

These examples can also be found in the `examples.ipynb` Jupyter notebook.

```python
import numpy as np
from nice_colorsys import rgb
from glasbeyish import glasbey
from matplotlib.colors import ListedColormap
```

## Generate a palette with 2 colors


```python
cm = ListedColormap([c.to_rgb() for c in glasbey(2)])
cm
```

    /home/andrew/miniconda3/envs/rna-clique/lib/python3.12/site-packages/glasbeyish/glasbey.py:106: RuntimeWarning: overflow encountered in exp
      if rng.random() <= min(1, np.exp((new_min - old_min)/temperature)):





<div style="vertical-align: middle;"><strong>from_list</strong> </div><div class="cmap"><img alt="from_list colormap" title="from_list" style="border: 1px solid #555;" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAgAAAABACAYAAABsv8+/AAAAGHRFWHRUaXRsZQBmcm9tX2xpc3QgY29sb3JtYXBDL89FAAAAHnRFWHREZXNjcmlwdGlvbgBmcm9tX2xpc3QgY29sb3JtYXABtCnOAAAAMHRFWHRBdXRob3IATWF0cGxvdGxpYiB2My45LjIsIGh0dHBzOi8vbWF0cGxvdGxpYi5vcmdhmcVTAAAAMnRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHYzLjkuMiwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZ08/WnQAAAE0SURBVHic7dZBFUAAFABBdNBAHP0zuCngPVr4h51JsMdd7/15FyDpvI7pBGDINh0AAPzPAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAI+gBFAwTXA7MD9gAAAABJRU5ErkJggg=="></div><div style="vertical-align: middle; max-width: 514px; display: flex; justify-content: space-between;"><div style="float: left;"><div title="#ef15fdff" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #ef15fdff;"></div> under</div><div style="margin: 0 auto; display: inline-block;">bad <div title="#00000000" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #00000000;"></div></div><div style="float: right;">over <div title="#3bfe21ff" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #3bfe21ff;"></div></div></div>



## Generate a palette with 12 colors


```python
cm = ListedColormap([c.to_rgb() for c in glasbey(12)])
cm
```




<div style="vertical-align: middle;"><strong>from_list</strong> </div><div class="cmap"><img alt="from_list colormap" title="from_list" style="border: 1px solid #555;" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAgAAAABACAYAAABsv8+/AAAAGHRFWHRUaXRsZQBmcm9tX2xpc3QgY29sb3JtYXBDL89FAAAAHnRFWHREZXNjcmlwdGlvbgBmcm9tX2xpc3QgY29sb3JtYXABtCnOAAAAMHRFWHRBdXRob3IATWF0cGxvdGxpYiB2My45LjIsIGh0dHBzOi8vbWF0cGxvdGxpYi5vcmdhmcVTAAAAMnRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHYzLjkuMiwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZ08/WnQAAAGISURBVHic7daxLShgGEBRbCDREoygIa/RYQCJAVQGUNlGp1E8olQZgAnUpmCFv/JF7jkT3PJunj99fW/8Ea83V9MJy67vjqYTllx+HkwnLDv9vzedsOTfy/N0wrLHnYfphGVnu/fTCUueTk+mE5Ydvl9MJyx529+eTlh2fPsxnbBsazoAAPh9BgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABA0A9w2BE9Bvv2OgAAAABJRU5ErkJggg=="></div><div style="vertical-align: middle; max-width: 514px; display: flex; justify-content: space-between;"><div style="float: left;"><div title="#48b4eaff" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #48b4eaff;"></div> under</div><div style="margin: 0 auto; display: inline-block;">bad <div title="#00000000" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #00000000;"></div></div><div style="float: right;">over <div title="#fab312ff" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #fab312ff;"></div></div></div>



## Use a seed for reproducibility


```python
cm = ListedColormap([c.to_rgb() for c in glasbey(12, seed=485)])
cm
```




<div style="vertical-align: middle;"><strong>from_list</strong> </div><div class="cmap"><img alt="from_list colormap" title="from_list" style="border: 1px solid #555;" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAgAAAABACAYAAABsv8+/AAAAGHRFWHRUaXRsZQBmcm9tX2xpc3QgY29sb3JtYXBDL89FAAAAHnRFWHREZXNjcmlwdGlvbgBmcm9tX2xpc3QgY29sb3JtYXABtCnOAAAAMHRFWHRBdXRob3IATWF0cGxvdGxpYiB2My45LjIsIGh0dHBzOi8vbWF0cGxvdGxpYi5vcmdhmcVTAAAAMnRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHYzLjkuMiwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZ08/WnQAAAGMSURBVHic7daxLShgGEBR5CUSEsWLRqWzh0SrZgKGUAgrqBQ6G2h1r2IMjQ0UFKzwV7683HMmuOXdvD28+974T3zt3EwnLDv4fJ9OWHL59DadsOxi9890wpLtv8fTCcuu9q6nE5ad359NJyx5fDidTlh28vE6nbDk3/PRdMKy/cOX6YRlW9MBAMDvMwAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAgn4AfhMRgR6dD34AAAAASUVORK5CYII="></div><div style="vertical-align: middle; max-width: 514px; display: flex; justify-content: space-between;"><div style="float: left;"><div title="#822093ff" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #822093ff;"></div> under</div><div style="margin: 0 auto; display: inline-block;">bad <div title="#00000000" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #00000000;"></div></div><div style="float: right;">over <div title="#fd09ffff" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #fd09ffff;"></div></div></div>




```python
cm = ListedColormap([c.to_rgb() for c in glasbey(12, seed=485)])
cm
```




<div style="vertical-align: middle;"><strong>from_list</strong> </div><div class="cmap"><img alt="from_list colormap" title="from_list" style="border: 1px solid #555;" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAgAAAABACAYAAABsv8+/AAAAGHRFWHRUaXRsZQBmcm9tX2xpc3QgY29sb3JtYXBDL89FAAAAHnRFWHREZXNjcmlwdGlvbgBmcm9tX2xpc3QgY29sb3JtYXABtCnOAAAAMHRFWHRBdXRob3IATWF0cGxvdGxpYiB2My45LjIsIGh0dHBzOi8vbWF0cGxvdGxpYi5vcmdhmcVTAAAAMnRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHYzLjkuMiwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZ08/WnQAAAGMSURBVHic7daxLShgGEBR5CUSEsWLRqWzh0SrZgKGUAgrqBQ6G2h1r2IMjQ0UFKzwV7683HMmuOXdvD28+974T3zt3EwnLDv4fJ9OWHL59DadsOxi9890wpLtv8fTCcuu9q6nE5ad359NJyx5fDidTlh28vE6nbDk3/PRdMKy/cOX6YRlW9MBAMDvMwAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAggwAAAQZAAAIMgAAEGQAACDIAABAkAEAgCADAABBBgAAgn4AfhMRgR6dD34AAAAASUVORK5CYII="></div><div style="vertical-align: middle; max-width: 514px; display: flex; justify-content: space-between;"><div style="float: left;"><div title="#822093ff" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #822093ff;"></div> under</div><div style="margin: 0 auto; display: inline-block;">bad <div title="#00000000" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #00000000;"></div></div><div style="float: right;">over <div title="#fd09ffff" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #fd09ffff;"></div></div></div>



## Limit the colors that can be generated

Here, we'll try to make a bluish color palette by discarding colors too far from blue.


```python
def color_dist(a, b):
    return np.linalg.norm(np.array(a.to_cieluv()) - np.array(b.to_cieluv()))

cm = ListedColormap([c.to_rgb() for c in glasbey(12, seed=485, limit=lambda x: color_dist(x, rgb(0, 0, 1)) < 100)])
cm
```




<div style="vertical-align: middle;"><strong>from_list</strong> </div><div class="cmap"><img alt="from_list colormap" title="from_list" style="border: 1px solid #555;" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAgAAAABACAYAAABsv8+/AAAAGHRFWHRUaXRsZQBmcm9tX2xpc3QgY29sb3JtYXBDL89FAAAAHnRFWHREZXNjcmlwdGlvbgBmcm9tX2xpc3QgY29sb3JtYXABtCnOAAAAMHRFWHRBdXRob3IATWF0cGxvdGxpYiB2My45LjIsIGh0dHBzOi8vbWF0cGxvdGxpYi5vcmdhmcVTAAAAMnRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHYzLjkuMiwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZ08/WnQAAAGLSURBVHic7daxLS5gGEBh5AqV8iYSpQGMIFGolUL8hVmEDbRWkEjuKlqJVsQErPBV3tyc55nglGf7cvfhe+s/cf54NZ2w7OLgcDphycndzXTCsrf96+mEJad/z6YTln1t3qcTlv27P5pOWHK8+TOdsOzp9WM6YcnXy/N0wrK9z9vphGU70wEAwO8zAAAQZAAAIMgAAECQAQCAIAMAAEEGAACCDAAABBkAAAgyAAAQZAAAIMgAAECQAQCAIAMAAEEGAACCDAAABBkAAAgyAAAQZAAAIMgAAECQAQCAIAMAAEEGAACCDAAABBkAAAgyAAAQZAAAIMgAAECQAQCAIAMAAEEGAACCDAAABBkAAAgyAAAQZAAAIMgAAECQAQCAIAMAAEEGAACCDAAABBkAAAgyAAAQZAAAIMgAAECQAQCAIAMAAEEGAACCDAAABBkAAAgyAAAQZAAAIMgAAECQAQCAIAMAAEEGAACCDAAABBkAAAgyAAAQZAAAIMgAAECQAQCAIAMAAEEGAACCfgBcsREwKJzvNQAAAABJRU5ErkJggg=="></div><div style="vertical-align: middle; max-width: 514px; display: flex; justify-content: space-between;"><div style="float: left;"><div title="#5a0589ff" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #5a0589ff;"></div> under</div><div style="margin: 0 auto; display: inline-block;">bad <div title="#00000000" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #00000000;"></div></div><div style="float: right;">over <div title="#a70dfeff" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #a70dfeff;"></div></div></div>



## Use a custom random color generator

In this example, we'll generate random colors with only blue components in the RGB color space. `glasbey` expects the generated colors to be in the CIELUV color space and won't automatically convert the colors from RGB to CIELUV for us, so we have to do that ourselves.


```python
rng = np.random.default_rng()
```


```python
def random_color(rng):
    return rgb(0, 0, rng.random()).to_cieluv()
    
cm = ListedColormap([c.to_rgb().safe() for c in glasbey(12, seed=485, random_color=random_color)])
cm
```




<div style="vertical-align: middle;"><strong>from_list</strong> </div><div class="cmap"><img alt="from_list colormap" title="from_list" style="border: 1px solid #555;" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAgAAAABACAYAAABsv8+/AAAAGHRFWHRUaXRsZQBmcm9tX2xpc3QgY29sb3JtYXBDL89FAAAAHnRFWHREZXNjcmlwdGlvbgBmcm9tX2xpc3QgY29sb3JtYXABtCnOAAAAMHRFWHRBdXRob3IATWF0cGxvdGxpYiB2My45LjIsIGh0dHBzOi8vbWF0cGxvdGxpYi5vcmdhmcVTAAAAMnRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHYzLjkuMiwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZ08/WnQAAAFlSURBVHic7dYxcUJRFADRH5TgAU9psEDHoAAt8ZM+Ew1g4b0mdzJ7joIt9+M4Hq/j3/ieDtjwNR2w6DYdsOFzOmDRz3TAht/pgA3X6YBF9+mADc/pgEXn6YANl+mAZafpAADg7xkAAAgyAAAQZAAAIMgAAECQAQCAIAMAAEEGAACCDAAABBkAAAgyAAAQZAAAIMgAAECQAQCAIAMAAEEGAACCDAAABBkAAAgyAAAQZAAAIMgAAECQAQCAIAMAAEEGAACCDAAABBkAAAgyAAAQZAAAIMgAAECQAQCAIAMAAEEGAACCDAAABBkAAAgyAAAQZAAAIMgAAECQAQCAIAMAAEEGAACCDAAABBkAAAgyAAAQZAAAIMgAAECQAQCAIAMAAEEGAACCDAAABBkAAAgyAAAQZAAAIMgAAECQAQCAIAMAAEEGAACCDAAABBkAAAgyAAAQZAAAIMgAAECQAQCAIAMAAEFvDzYIJ8qhpTAAAAAASUVORK5CYII="></div><div style="vertical-align: middle; max-width: 514px; display: flex; justify-content: space-between;"><div style="float: left;"><div title="#000085ff" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #000085ff;"></div> under</div><div style="margin: 0 auto; display: inline-block;">bad <div title="#00000000" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #00000000;"></div></div><div style="float: right;">over <div title="#0000a8ff" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #0000a8ff;"></div></div></div>


