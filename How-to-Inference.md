# Notes how to run SkexGen

## Installation

To be able to install pythonocc I would strongly advice using conda. It seems rather complicated to install it without the conda package.

What worked for me:
```
conda create --name=pyoccenv python=3.9
conda activate pyoccenv
conda install -c conda-forge pythonocc-core=7.7.2
conda install pytorch==2.2.1 torchvision==0.17.1 torchaudio==2.2.1 -c pytorch
pip install -r requirements.txt
```
torchvision and torchaudio can probably be removed. I have not tested the Docker image because of its size of 10GB.

## Additional notes

* If you want to run this code on a local machine without a GPU, please switch to the `run_on_cpu` branch. I only tested the inference part of the code. If you want to be able to execute the training scripts, additional modifications will have to be made. 
* Instead of going through the preprocessing steps with the DeepCAD dataset, I justed downloaded the pre-processed dataset from the provided link (see below in the original README). It has to be moved into the `data` directory, i.e. `data/cad_data/...`.
* A link for the pretrained models can be found below. The directory proj_log should be extracted and moved into the root of this repository.
* In addition to the command line flags, there are a few global variables in each script. For instance, in the sample.py file there are the three variables NUM_SAMPLE, NUM_THREADS and BS to control how many random CAD models you want to create.