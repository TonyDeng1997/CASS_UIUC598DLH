# CS598 DLH Group 104

Will Charles(wc40@illinois.edu) 
Hanfei Deng(hdeng11@illinois.edu) 
Stefan Wang(yifanw23@illinois.edu)


# PyTorch implementation of **CASS**, from the following papers for:


[CASS: Cross Architectural Self-Supervision for Medical Image Analysis](https://arxiv.org/abs/2206.04170). 

# Original Github Repo
https://github.com/pranavsinghps1/CASS
# Video Explanation 
https://www.youtube.com/watch?v=h0_fsf-evKY
# Dateset Used
[Brain Tumor MRI Dataset](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset). 

# Instructions 
To run with our exact configuration, first set up a virtual machine on Google’s compute engine. 
- Select
V100 for the GPU, 30GB of RAM for the CPU,  and for the machine image
select Deep Learning VM with CUDA 11.8, M116, Debian 11, Python 3.10.
- Enable “Allow HTTP traffic” and “Allow HTTPS traffic”. 
- Then reserve a static external IP and create a new Firewall rule.  In the
firewall rule under Protocols and ports, select “Specified protocols and
ports” and enter 5000 in the TCP section.
- Open the SHH terminal enter the following commands:
  ```
	wget https://repo.anaconda.com/archive/Anaconda3-2023.03-1-Linux-x86_64.sh
	bash Anaconda3-2023.03-1-Linux-x86_64.sh
	source ~/.bashrc
	jupyter notebook --generate-config
	vim ~/.jupyter/jupyter_notebook_config.py
  ```
- Add the following lines of code to the configuration file:
  ```
	c.NotebookApp.ip = '*'
	c.NotebookApp.open_browser = False
	c.NotebookApp.port = 5000
  ```
- Then open the jupyter notebook with:
	```
	jupyter-notebook --no-browser --port=5000
	```
- Go to your browser and go to http://~your static external ip~:5000
- Now run the notebook.


# Explanation of Files 

### requirements.txt

This file includes all packages we use for this model

### DL4H_Team_104_final.ipynb
This file contains the everything you might need to run CASS. It uses the brain tumor MRI dataset and contains the model configuration, training and decleration. This file is a jupyter notebook. Please run it sequentially.

### DL4H_Team_104_Final.pdf 
Pdf version of the jupyter notebook. 

### cass-CNN-100epoch-16batch-finetune.pt

CNN model pretrain 100 epochs and finetune 50 epochs. Please load it to evualuation section to see the result.

### cass-CNN-200epoch-16batch-finetune.pt

CNN model pretrain 200 epochs and finetune 50 epochs. Please load it to evualuation section to see the result.

### cass-CNN-50epoch-16batch-finetune.pt
CNN model pretrain 50 epochs and finetune 50 epochs. Please load it to evualuation section to see the result.

### testing.csv
label pair for testing dataset. Could be generated with the code in Data section as well 

###training.csv
label pair for training dataset. Could be generated with the code in Data section as well 

