---
layout: page
title: End of Week Progress Update 7/6/18
---

# Progress
* Prepared William's computer for training iTracker ML Model
  * Downloaded and unpacked GazeCapture data
  * Updated Nvidia drivers and Cuda toolkit (Version 9.0) to interface with Tensorflow
* Created development workflow pipeline for continued development of new features (useful for iteration & testing after iTracker proof of concept)
* Implemented additional features for iTracker
  * Model checkpoints to halt and resume training
  * Learning Rate Scheduler to allow for variable training rates
  * UI tweaks to provide improved feedback on model training progress
  * Performance improvements to avoid unecessary file I/O
  * Beginning implementation of TensorBoard to monitor training progress
* Current status:
  * Model is training on William's Computer (Nvidia GeForce GTX 1080) with 80 subjects (50 training, 20 validation, 10 testing) 
# Findings
  * Model execution time is currently bottlenecked by File I/O & Memory space
    * Traditional hard drives do not have enough bandwidth to train model at reasonable speed
    * SSD is significantly faster, but is still (likely) bottlenecking model execution speed. Additional testing is required to verify this bottleneck.
    * Tensorflow execution speed can be improved with increased V-RAM
    * Training and iteration will only be possible on Nvidia DGX-1
    
# Next Steps
* Evaluate model performance from preliminary training on William's computer
* Create visualizer to visualize the output of the model
  * Should be able to see actual gaze direction and predicted gaze direction for a given picture
* Train model on DGX-1 with full dataset to fully replicate results from MIT
* Feed new gaze data (not included in dataset) to model and test performance
* Modify ML model to produce the gaze vector, rather than gaze coordinates
* Iterate and improve peformance
