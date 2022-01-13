## Set up the Development Environment for Deep Learning Development (Pytorch)

We will use Pytroch framework for our hands-on deep learning session. In this markdown, I will briefly introduce how to configure related dependecies in Conda environmnt.

Please note that it is recommended to follow the order of the following steps, especially for step 3 and step 4. I met libraries versions conflict if installing pytorch after installing other libraries listed in step 4.

1. Create a new (standalone) conda environment for the development of deep learning related applications.
```
conda create -n torch_dev python=3.8
```
2. Activate the newly created environment. All the related python libraries will be installed in this environment.
```
conda activate torch_dev
```
You should be able to see **(torch_dev)** in your command line prompt.

3. Install Jupyter Lab/Jupyter Notebook (for completing)
```
# jupyter lab
conda install -c conda-forge jupyterlab
# classic jupyter notebook
conda install -c conda-forge notebook
# start jupyter lab server
jupyter-lab
# start jupyter notebook server
jupyter notebook
```

4. Install Pytorch (the default installed version 1.10.1 as of 01/13/2022). The actual command varies depending on whether you have Nvidia GPU available and etc. Here I assume you only have CPU available.

```
# For MAC OS
conda install pytorch torchvision torchaudio -c pytorch
# For Linux
conda install pytorch torchvision torchaudio cpuonly -c pytorch
# For Windows
conda install pytorch torchvision torchaudio cpuonly -c pytorch
``` 
You can refer to this [pytorch official page](https://pytorch.org/) for other installation options. If you have GPU available for model training, you can specify the CUDA version in this page and find the correponding installation command in the "Run this Command" tab.

5. Install other related python scientific computation libraries.
```
# install sklearn
conda install -c conda-forge scikit-learn 
# install pandas
conda install pandas
# install matplotlib
conda install -c conda-forge matplotlib
# install skimage
conda install -c anaconda scikit-image
```

6. Validate you have installed pytorch successfully.
```
# start an ipython interactive session
ipython

# Below are python commands
import torch
print(torch.__version__) #1.10.1
x = torch.Tensor([1, 2, 3])
print(x) #tensor([1., 2., 3.])
```