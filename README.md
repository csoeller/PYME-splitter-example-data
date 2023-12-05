# PYME-splitter-example-data

This repository contains a few PYME data files to test a few features of splitter support in PYME.

Currently contains:

* `28_11_series_A-extracted.h5`: this one raises an error upon `Unsplit`
* `28_11_series_B-extracted.h5`: also raises an error upon `Unsplit`
* `28_11_series_C-extracted.h5`: this one works as anticipated upon `Unsplit`

Of note, IMHO, all should generate split data with a width of 550 pixels, just ROI height varies between series.

When using `PYME.localization.splitting.get_splitter_rois()` all three cases work fine, e.g. in a shell, e.g. with `28_11_series_A-extracted.h5`, ones gets:

```python
from PYME.localization.splitting import get_splitter_rois
xgs, xrs, ygs, yrs = get_splitter_rois(image.mdh, image.data_xytc.shape)
image.data_xytc[xgs,ygs,0,0].shape
(550, 776, 1)
image.data_xytc[xrs,yrs,0,0].shape
(550, 776, 1)
```
