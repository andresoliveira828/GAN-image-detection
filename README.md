# GAN-image-detection
This repository contains a GAN-generated image detector developed to distinguish real images from synthetic ones.
The complete description of the methodology is available [here](https://arxiv.org/pdf/2203.02246.pdf).
The detector is based on an ensemble of CNNs.
The backbone of each CNN is the EfficientNet-B4.
Each model of the ensemble has been trained in a different way following the suggestions presented in [this paper](https://ieeexplore.ieee.org/abstract/document/9360903) in order to increase the detector robustness to compression and resizing.

## Run the detector

### Prerequisites
1. Create and activate the conda environment
```bash
conda env create -f environment.yml
conda activate gan-image-detection
```
2. Download the model's weights from [this link](https://www.dropbox.com/s/n1boisish8m6aoj/weights.zip?dl=0) and unzip the file under the main folder
```bash
wget https://www.dropbox.com/s/n1boisish8m6aoj/weights.zip?dl=0
unzip weigths.zip
```

### Test the detector on a single image
We provide a simple script to obtain the model score for a single image.
```bash
python gan_vs_real_detector.py --img_path $PATH_TO_TEST_IMAGE
```

## Performance
We provide a [notebook](https://github.com/polimi-ispl/GAN-image-detection/blob/main/roc_curves.ipynb) with the script for computing the ROC curve for each dataset.

## How to cite

The proposed method has been presented in this [paper](https://arxiv.org/pdf/2203.02246.pdf):
```
S. Mandelli, N. Bonettini, P. Bestagini, S. Tubaro, "Detecting Gan-Generated Images by Orthogonal Training of Multiple CNNs", IEEE International Conference on Image Processing (ICIP), 2022, doi: 10.1109/ICIP46576.2022.9897310.
```
Training procedures have been carried out following the suggestions presented in the following paper:
```
S. Mandelli, N. Bonettini, P. Bestagini, S. Tubaro, "Training CNNs in Presence of JPEG Compression: Multimedia Forensics vs Computer Vision", IEEE International Workshop on Information Forensics and Security (WIFS), 2020, doi: 10.1109/WIFS49906.2020.9360903.
```

Bibtex:
```bibtex
@INPROCEEDINGS{mandelli2022detecting,
  author={Mandelli, Sara and Bonettini, Nicolò and Bestagini, Paolo and Tubaro, Stefano},
  booktitle={2022 IEEE International Conference on Image Processing (ICIP)}, 
  title={Detecting Gan-Generated Images by Orthogonal Training of Multiple CNNs}, 
  year={2022},
  volume={},
  number={},
  pages={3091-3095},
  doi={10.1109/ICIP46576.2022.9897310}}

@INPROCEEDINGS{mandelli2020training,
  author={Mandelli, Sara and Bonettini, Nicolò and Bestagini, Paolo and Tubaro, Stefano},
  booktitle={IEEE International Workshop on Information Forensics and Security (WIFS)}, 
  title={Training {CNNs} in Presence of {JPEG} Compression: Multimedia Forensics vs Computer Vision}, 
  year={2020},
  doi={10.1109/WIFS49906.2020.9360903}}
```

## Credits
[Image and Sound Processing Lab - Politecnico di Milano](http://ispl.deib.polimi.it/)
- Sara Mandelli
- Nicolò Bonettini
- Paolo Bestagini
- Stefano Tubaro
