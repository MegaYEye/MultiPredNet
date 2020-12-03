# MultiPredNet

A multimodal predictive coding implementation for place recognition.

## Dependencies:

- Python 3.5 or higher
- Tensorflow 2.0 or higher
- MATLAB 2020b with valid License
- ROS (any version)

## Also required:

- A ROSbag file, generated from the NeuroRobotics Platform Whiskeye Experiment.

**OR**

- Alternatively, sample ROSbag and MATLAB files are available at **dataset_link**

NB: If your data has already been unpacked from its ROSbag, then ROS nor the ROSbag is required. Use the generated .mat files instead

## Installing Dependencies:

- Visit https://www.python.org/ to download Python. Install it.
- Open Terminal and run `pip install tensorflow`
- Visit https://www.mathworks.com/ to download MATLAB 2020b. Install it.
- MATLAB will prompt for a license; enter your organisation credentials to obtain the license. MATLAB will find and activate automatically.

## Configuration Steps:

- Clone this repository
- (If ROSbag is not unpacked) open Terminal and run `rosbag play <bagname.bag>` where <bagname> is the name of your generated ROSbag
- (If ROSbag is not unpacked) open MATLAB and run the **todo.mat** script to interpret the ROSbag. Once this is done you will have several .mat files generated
- Move your training and test data to a suitable folder

- Alter the three scripts below by substitute the following paths with your own. These can be anywhere within your user directory:

### MultiPredNet Training Script

Within `python_multiprednet_train_showcase.py`:

- [Line 61]: assign your training .mat data file location to the `data_path` variable
- [Line 63]: assign a suitable save path to the `save_path` variable; it is recommended to create a new, empty folder for this purpose
- [Line 64]: assign a suitable load path to the `load_path` variable; this can be the same as your `save_path`

### MultiPredNet Inference Script

Within `python_multiprednet_gen_reps_showcase.py`:

- [Line 14]: assign trained model location to the `model_path` variable. This is like to be the same as `save_path` within the Training Script
- [Line 15]: assign training data location to the `tr_data_path` variable
- [Line 16]: assign test data location to the `ts_data_path` variable
- [Line 17]: assign output location for representations to the `save_path` variable. This can be the same as `save_path` within the Training Script if you'd like, but this isn't essential

### MultiPredNet Figure Script

Within `matlab_multiprednet_figures_showcase.m`:

- [Line 20 and 22]: pass test data location to the `load()` functions
- [Lines 33, 35, 48, 50, 59 and 61]: pass output representations (from Inference Script's `save_path`) location to the `load()` functions

### Finally

- Save your changes to these files

## Running the Experiment

Within Terminal or a suitable IDE:

1) Run `python_multiprednet_train_showcase.py`. Tensorflow will start up and run the training code. Wait until console output stops
2) Run `python_multiprednet_gen_reps_showcase.py`. The inference process will begin. Wait until console output stops

Within MATLAB:

1) Run `matlab_multiprednet_figures_showcase.m`. Figures will be generated showing the Representational Simularity Matrices. These can be compared to our results at **link**
