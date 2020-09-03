# Learning Once and for All ?
# On the Input Sensitivity of Configurable Systems

Dear ICSE reviewers,

In this repository, you can consult the code, the data and the results related to our submission "Learning Once and for All? On the Input Sensitivity of Configurable Systems".



# GOAL

In this paper, we want to prove that **input videos have an influence on x264 compression performances**.

In particular, the first research question is :
RQ1. Do Input Videos Change Performances of x264 Configurations?

We aim at quantifying the differences of x264's performances due to input videos, and how input videos interact with software features.

Once this statement is proved, we use the properties of input videos (e.g. height, width, spatial and temporal complexities, etc.) to **find a configuration optimizing a performance** (in our case minimize the bitrate of video compressions).

We propose an approach, Inputec, that finds a configuration tailored for inputs.



# Material

## Introduction

As an introduction, let us separate two different parts of the experimental protocol;

- **Measurements** - first of all, we measure x264 performances, for a given set of 201 configurations and a dataset of 1397 videos.

- **Analyze** - we then analyze the obtained measurements with python scripts.



### I- Measurements

The third contribution of the paper states that for replicability, we provide a comprehensive **data**set of configurations’ measurements. 

We provide instructions useful to **replicate** or reproduce our dataset.

#### I- 1. Data

Data are available in the "data" folder. 

For this experiment, showing that input videos have an influence on video compression's performances, we first need **videos** to encode.

##### I- 1. a-] Encoded videos

We used the dataset of videos defined in "Youtube UGC Dataset for Video Compression Research" by Wang et al. (see their [publication](https://arxiv.org/abs/1904.06457)).

Since it is a huge dataset of videos (about 3 terabytes of videos), we did not duplicate it.

However, these videos are available in the [Youtube UGC Dataset cloud](https://console.cloud.google.com/storage/browser/ugc-dataset/original_videos;tab=objects?prefix=)

Alternatively, and to see more concretely the content of each video, you can visualize them by clicking on 'Explore' in the Youtube UGC Dataset homepage:

https://media.withyoutube.com/

For each of these videos, and for 201 configurations, we compressed the video with x264 and measured five performances (bitrate, cpu consumption, frame encoded per second, encoded size of videos and encoding time). For each video, there is a related .csv file that contains these **measurements**.

##### I- 1. b-] Measurements

All these measurements are in the data/res_ugc folder, follow this [link](https://anonymous.4open.science/repository/df319578-8767-47b0-919d-a8e57eb67d25/data/ugc/res_ugc/).

We shared our measurements here, in order to make it accessible for everyone: https://zenodo.org/record/3928253

You may be interested to **replicate** the measurements with other datasets of videos.

#### I- 2. Replication

We provide a docker image to build (i.e. a Dockerfile) to replicate or reproduce the measurements (i.e. see these [files](https://anonymous.4open.science/repository/df319578-8767-47b0-919d-a8e57eb67d25/data/ugc/res_ugc/)).

To use it, you can follow the steps in this directory:

https://anonymous.4open.science/repository/df319578-8767-47b0-919d-a8e57eb67d25/replication/dataset_building/ugc/

The "replication" folder details the configuration of our server (hardware details, operating system distribution and version, software version) and provides a Dockerfile to build in order to replicate the measurements.



### II- Analyze

To analyze these measurements, we use **code**, that gives **results**, depicted and discussed in the submission paper.


#### II- 1. Code

The code is in the "src" folder.

We highly recommend to consult this page, containing a preview of the (heavily commented) code leading to the results of the paper; 

https://anonymous.4open.science/repository/df319578-8767-47b0-919d-a8e57eb67d25/src/main/bitrate.md

If you want to run it, we provide a [python file](https://anonymous.4open.science/repository/df319578-8767-47b0-919d-a8e57eb67d25/src/main/bitrate.py) generating these results and all the graphs of the paper.


#### II- 2. Results

Results produced by the code, previously presented in subsection II-1.

See README.md in the results folder.


#### II- 3. Resources

Additional information about the experiment, the x264 configuration knowledge (a.k.a. domain knowledge), and ideas explored during the redaction of the paper!

See README.md in the resources folder.


# Acknowledgement

We would like to thank Yilin Wang for the explanations about input properties.


