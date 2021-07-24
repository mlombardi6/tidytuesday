
# Introduction

When I first saw the US droughts dataset I automatically (and quite predictably?) thought of ways to represent this spatially. News outlets such as the [New York Times](https://www.nytimes.com/interactive/2021/06/11/climate/california-western-drought-map.html) and the [CNN](https://www.cnn.com/2021/06/17/weather/west-california-drought-maps/index.html) had already covered this abundantly in June with a selection of heatmaps and choropleth maps. 

A way to add some flavour would be incorporate an animation to represent the flow of time, as drought phases come and go. One way to approach this would have been through spatial data points and density maps (but in the provided dataset areal are provided), or adding further inputs, like @katie_press showed [here](https://twitter.com/katie_press/status/1417574749442564102). 

Of course the data collection is organised in week frames and this adds to the temptation of creating an animation to represent the flow of time anyway.


# Some context

Dry and wet cycles are dependent on a number of factors including geography, topology and climate drivers. Drought phases in the US can be explained by changes in the track of extratropical cyclones, which can occur during climate cycles such as the El Niño-Southern Oscillation, or ENSO, as well as the North Atlantic Oscillation, Pacific Decadal Oscillation, and Atlantic multidecadal oscillation. The country's contiguous western and especially southwestern region has experienced widespread drought since about year 2000 (https://en.wikipedia.org/wiki/Droughts_in_the_United_States).


# My visualisation

I was interested in a visualisation that could manifestly represent the cyclic nature of wet and dry phases across the US and that could highlight some of those most critical periods in the last 20 years, and the states mostly impacted by it (the south west). 

To do this I relied on some functionalities of the [gganimate package](https://github.com/thomasp85/gganimate) and a cumulative metric based on the proportion of area and population affected by a drought level of D3 severity or more.  


| Drought Level | Label
| :---: | :---: | 
| None | no drought |
| D0 |	abnormally dry |
| D1 |	moderate drought |
| D2 |	severe drought |
| D3 |	extreme drought |
| D4 |	exceptional drought | 


To add some fun I used `av_renderer()` which allows to combine your animation with an audio track. My choice was 'Rain' (The Beatles). Because the track is about 2 minutes and 55 seconds long (175 seconds) I needed a certain number of frames to make the video fit with the audio. After some tweaking I found that 15 frames per seconds was a balanced choice to preserve fluidity and speed of the transition states. Therefore $nframes = 15 \text{fps} \times 177 seconds$.

Enjoy. 







