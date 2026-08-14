# Diabetic Retinopathy (DR) CNN Classifier

Project for classification of retinal images to detect DR blindness using convolutional neural networks.

## Dataset 
[APTOS 2019 Blindness Detection](https://www.kaggle.com/c/aptos2019-blindness-detection),
A Kaggle competition dataset containing thousands of labeled images with 5 classes for severity of DR.

## Results

| | No DR | DR Present |
|---|---|---|
| Precision | 0.96 | 0.97 |
| Recall | 0.97 | 0.96 |
| F1 | 0.97 | 0.97 |

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

## Limitations

No cross validation, only using a single train/val/test split in current version.

Relatively small dataset as my GPU would struggle to train in reasonable time past tens of thousands of samples and with more layers to tune. I would like to repeat similar projects in future with larger training and test sets, possibly using cloud based GPU processing on services such as Google CoLab

## Future expansions

I will implement Grad-CAM to further understand the data and which parts of the images are heavily weighted in the classification process.

I would like to expand this project into a 5-class classification covering each severity of DR blindness, this project exists to establish a baseline and learn best practices for future multi-class versions.

In future iterations of this project I will experiment with image preprocessing and explore common practicces for processing FUNDUS images.

As I used a pretrained model with frozen layers, I decided to use standard ImageNet weights (mean and std). In future I would like to experiment with fully training the network from scratch, in which case I would normalise the dataset. 

## References

The dataset used is from [APTOS 2019 Blindness Detection](https://www.kaggle.com/c/aptos2019-blindness-detection) 
Kaggle competition.