# Diabetic Retinopathy (DR) CNN Classifier

Project for classification of retinal images to detect DR blindness using convolutional neural networks.

## Dataset 
[APTOS 2019 Blindness Detection](https://www.kaggle.com/c/aptos2019-blindness-detection),
A Kaggle competition dataset containing thousands of labeled images with 5 classes for severity of DR.

## Setup

Tested on WSL2 (Ubuntu) with an NVIDIA GPU.

1. Using a [Kaggle account](https://www.kaggle.com), access the [APTOS 2019 Blindness Detection](https://www.kaggle.com/c/aptos2019-blindness-detection) and accept the competition rules, as well as validating your account with a phone number
2. Clone this repository
3. Create conda environment using: conda create -n retina-cnn python=3.12 -y && conda activate retina-cnn
4. Install torch/torchvision/torchaudio using the correct command for your system from pytorch.org/get-started
5. Install dependencies using: pip install -r requirements.txt
6. Create a Kaggle API token via Kaggle settings page and save it locally using: mkdir -p ~/.kaggle
echo "YOUR_API_TOKEN" > ~/.kaggle/access_token
chmod 600 ~/.kaggle/access_token
7. Download the dataset using this command in the retina-cnn directory: mkdir -p data && cd data && kaggle competitions download -c aptos2019-blindness-detection --unzip
8. Run ipynb files in /notebooks

## References

The dataset used is from [APTOS 2019 Blindness Detection](https://www.kaggle.com/c/aptos2019-blindness-detection) 
Kaggle competition.