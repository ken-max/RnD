---
layout: page
title: Progress Update 7/3/18
---

# Progress Update 7/3/18
* Built custom pre-processor to prepare data to feed into machine learning model
  * Handles all steps from taking raw data to feeding to model
  * Provides ability to the data being fed to model
* Made project portable to make it easy to run on various machines
* Tested execution on small dataset (5 subjects, ~100 pictures)
* Currently testing execution and training on full dataset (1474 subjects, ~2.5 million pictures) to replicate results found in [Eye tracking for everyone](http://gazecapture.csail.mit.edu/) (Krafka et al., 2016)

# Next Steps
* Finish training model on William's computer and measure model performance
* Train the model on the DGX-1 for a longer duration of time
* Add the ability to save current training progress so that execution can be stopped and resumed without having to restart training
* Remove the requirement to unzip data every execution
* Create visualizer to visualize the output of the model
  * Should be able to see actual gaze direction and predicted gaze direction for a given picture
* Feed new gaze data (not included in dataset) to model and test performance
* Modify ML model to produce the gaze vector, rather than gaze coordinates
* Iterate and improve peformance
