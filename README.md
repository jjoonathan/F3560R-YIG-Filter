# F3560R Characterization

I snatched a nifty YIG filter off ebay the other day. I bought it on account of the 1.85mm connectors, as they suggested a frequency range that was relevant to my interests. Of course, it was still a gamble, so the next step was to characterize the filter and see if the gamble paid off. This repo tells the story of said characterization.

Spoiler alert: it paid off :)


<img src="F3560R.jpg" width="800"/>

## Passband Response

This module's "deliverable" is a current-controlled bandpass characteristic. Put in a current I, get a bandpass centered at frequency f. Up to 50GHz, I can characterize this with my repaired 8510C network analyzer. Results here: https://jjoonathan.github.io/sweep1.html

* _F3560R Data Gathering.ipynb_: controls instruments to conduct measurement.
* _F3560R YIG Data Fit.ipynb_: fits a model.

## Leakage Response

Above 50GHz, I have to use an "improvised" scalar analysis setup. The noise floor is rather high, but it demonstrates an important point: the energy demand goes parabolic at 60GHz, but the YIG becomes leaky between 65GHz and 75GHz and this could be used to extend the useful range of a spectrum analyzer slightly beyond the upper frequency limit of the YIG. Cool!

<img src="F3560R YIG Leakage.png" width="800"/>


## I(f) -- Current Demand

The frequency is controlled by current, so the key engineering question is: how much current (and power) is required for a given frequency? A quantitative answer to this question allows for frequency planning and controller design.

<img src="F3560R YIG Main Coil Current.png" width="800"/>
<img src="F3560R YIG Main Coil Power Consumption.png" width="800"/>

## Residuals

How good is the polynomial spline model at capturing the slow frequency response of the YIG? The residual plot tells us.

<img src="F3560R YIG Main Coil Current Model Residual.png" width="800"/>