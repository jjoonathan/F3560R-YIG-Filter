# F3560R Characterization

I snatched a nifty YIG filter off ebay the other day. I bought it on account of the 1.85mm connectors, as they suggested a frequency range that was relevant to my interests. Of course, it was still a gamble, so the next step was to characterize the filter and see if the gamble paid off. This repo tells the story of said characterization.

Spoiler alert: it paid off :)


<img src="F3560R.jpg" width="800"/>

## Frequency Response

The "deliverable" here is a current-controlled bandpass filter. Up to 50GHz, I can characterize this with my repaired 8510C network analyzer. Results here: https://jjoonathan.github.io/sweep1.html

Above 50GHz, I have to use an "improvised" scalar analysis setup. Results:

<img src="F3560R YIG Leakage.png" width="800"/>


# I(f) -- Current Demand

The frequency is controlled by current, so the key engineering question is: how much current (and power) is required for a given frequency? A quantitative answer to this question allows for frequency planning and controller design.

<img src="F3560R YIG Main Coil Current.png" width="800"/>
<img src="F3560R YIG Main Coil Power Consumption.png" width="800"/>

# Residuals

How good is the polynomial spline model at capturing the slow frequency response of the YIG? The residual plot tells us.

<img src="F3560R YIG Main Coil Current Model Residual.png" width="800"/>