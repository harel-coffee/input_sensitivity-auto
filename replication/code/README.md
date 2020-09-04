## Replication - code

We provide you some instructions to launch the code resulting to the graphs printed in the paper.


## 1. Install Docker

If docker is not installed on your laptop, just follow this link; https://docs.docker.com/get-docker/

When it's done, you should be able to run the following command : 

```docker --version```

    >```Docker version 19.03.12, build 48a66213fe```


Useful links if you struggle with docker installation :

- https://www.ibm.com/cloud/blog/installing-docker-windows-fixes-common-problems

- https://medium.com/@randima.somathilaka/docker-engine-install-fails-in-ubuntu-3e70762c2187

- https://runnable.com/docker/install-docker-on-macos


## 2. Build the image of the container

Check that you are in the root/replication/code/ folder, and run the following command;

```sudo docker build -t input_code .```

You will need administrator privileges to run the command. It will build a docker image in a 18.04 linux environment.

You can skip the following lines of information and go straight to 3.

Additionally, you can open the Dockerfile in this directory to see the different steps of the building.

- First, we use a linux 18.04 environment, we update the packages

- We install git to download code (from an "anonymous account")

- We install python (version 3) and the different libraries uselful to run the code

- We clone a git repository (anonymous account, you can check the repo) to run the bitrate.py scripts

- We create an empty directory for results


## 3. Launch the code

To access the container, just type:

```sudo docker run -it input_code```

You will then enter in the container environement. Then, got in the script directory :

```cd code/src/main```

And launch the python script :

```python3 bitrate.py```

In the command line outputs, you will see the outputs (as in the [outputs.txt](https://anonymous.4open.science/r/df319578-8767-47b0-919d-a8e57eb67d25/replication/code/outputs.txt) file) printed and explained in the related [markdown](https://anonymous.4open.science/r/df319578-8767-47b0-919d-a8e57eb67d25/src/main/bitrate.md).

The python script is relatively long to run entirely (at least 15 minutes if you have a good laptop). Once the run is finished, you can attest that the results directory contains the figure printed in our paper:

```ls ../../results```

We apply modifications to corrmatrix-ugc-dendo-Spearman-kbs.pdf (i.e. convert it to png, add explanations about the scale and highlight groups), but the content (correlogram and dendograms) is the same as corrmatrix_modif.png (i.e. figure 1).

Figure 3 is just an overview of the approach, and is not an output of the code.

### See the repository for the files ; https://github.com/anonymous4opens/code

