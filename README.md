# Multi-Objective Optimization for Sparse Deep Neural Network Training

Contained within this repository is the source code corresponding to our paper titled "Multi-Objective Optimization for Sparse Deep Neural Network Training". A new Multi-Task Learning model architecture is introduced, namely the Monitored Deep Multi-Task Network (MDMTN). The framework for conducting experiments is based on PyTorch. The code has been tested within the Python 3 environment using JupiterLab, and necessitates the use of some Python packages: ```pytorch, torchvision, numpy, Pillow, scipy,```
and ```sklearn.``` 
We provide the (code to generate the) newly introduced Cifar10Mnist dataset in ```/Data_loaders/Create_Cifar10Mnist_dataset.py```.

<!--
<div style="text-align:center;">
    <img src="/Images/MDMTN_diag_new.jpg" alt="Monitored Deep Multi-Task Network" width="550" height="300">
</div>
-->

<figure class="image" style="text-align:center;">
  <img src="/Images/MDMTN_diag_new.jpg">
  <figcaption>Figure 1. Diagram of the Monitored Deep Multi-Task Network (MDMTN) with two main tasks. The task-specific monitors are designed to capture task-specific information that the shared network may miss.</figcaption>
</figure>

## USAGE

The script ```Train_and_Test.py```
gathers the helper functions from ```/src/utils/``` for training and testing a model on a dataset, given a preference vector.

We provide scripts for training an MDMTN model on the Cifar10Mnist dataset using our methodology as the default setting. However, these scripts are adaptable and applicable to variations such as the HPS model architecture, the MultiMnist dataset, and the MGDA method. This flexibility is enabled through the utilization of the config.py file.

To train a model for a specific preference vector $k$ while inducing sparsity, execute the script ```“example_mdmtn_cm.py”```. 
For training a model with the Multiple Gradient Descent Algorithm (MGDA), run the script ```“example_mdmtn_mgda_cm.py”```.

Use the script named ```"twoDpf_study_mdmtn_cm.py"``` for the additional (2D) Pareto front study we conducted on the model architectures. This required first finding the preference vector that yields the best model performance and saving the obtained model in the directory `src/Sparse_models/`.

## ACKNOWLEDGEMENTS

We utilize specific code segments from [Sener Ozan and Vladlen Koltun](https://github.com/isl-org/MultiObjectiveOptimization)'s work 'Multi-task learning as multi-objective optimization' to train a model using the Multiple Gradient Descent Algorithm (MGDA). Additionally, we incorporate code from [Zhang Dejiao et al.](https://github.com/Dejiao2018/GrOWL)'s paper 'Learning to Share: Simultaneous Parameter Tying and Sparsification in Deep Learning' to implement GrOWL as the secondary objective function used. Moreover, we consider the work of [Mishkin Dmytro and Jiri Matas](https://github.com/shunk031/LSUV.pytorch) in 'All You Need is a Good Init' for the initialization of our models.

## CONTACT
For any question, you can contact [Sedjro S. Hotegni](https://shsalomon.github.io/).
