# Description

This is an implementation of the paper "Revealing speckle obscured living human retinal cells with artificial intelligence assisted adaptive optics optical coherence tomography". 

# System Requirements

### Prerequisites

- Windows 10
- NVIDIA GPU +CUDA (tested on NVIDIA TITAN V, CUDA 11.7)

### Installation

- Install [Anaconda](https://www.anaconda.com/products/distribution)
- In the anaconda prompt:
```
conda create -n <newenv> python=3.7.13
conda activate <newenv>
cd RPE-recovery-DL
pip install -r requirements.txt 
cd src
```

# Demo

### Test

- A part of the test dataset has been deposited in `./data/test_data`. The
folder contains eight speckled images which are input to the model
`(./data/test_data/input)`. 
- Run `python test_model.py` to test the trained model whose weights are
deposited in `./data/trained_model`
- The results are stored in `./data/test_data/result`
- The ground truth images are provided in `./data/test_data/ground-truth`

### Train

- To train the model on custom data, run 
```
python train_model.py \
    --path-gt <path to training ground truth images> \
    --path-input <path to training input images> \
    --img-width <width of training images> \
    --img-height <height of training images> \
    --bs <batch size> \
    --epoch <number of epochs>
```

### Example

Single acquired speckled RPE image:

<img src="assets/speckledRPE.png" width="512" height="512" />

P-GAN recovered RPE:

<img src="assets/PGANRecoveredRPE.png" width="512" height="512" />



Ground truth averaged RPE:

<img src="assets/groundtruthAveragedRPE.png" width="512" height="512" />

