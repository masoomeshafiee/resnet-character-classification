# ResNet Character Classification

[![Python](https://img.shields.io/badge/python-3.9%2B-blue.svg)](https://www.python.org/)
[![Framework](https://img.shields.io/badge/framework-PyTorch-orange.svg)](https://pytorch.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

This project explores **deep learning for image classification** using **ResNet architectures**.  
I classify grayscale images combining **Japanese numerals** and **EMNIST characters** (letters + digits).  

I evaluate and compare four models:
- **ResNet50** (baseline)
- **Modified ResNet50** (with additional layers)
- **ResNet152**
- **Modified ResNet152**

---

## Features
- **Preprocessing**: image resizing (28×28 → 224×224), normalization, bilinear interpolation 
- **Models**: Different Deep Learning architecture: ResNet50, ResNet152, and modified variants with extra FC layers  
- **Training**: Cross-entropy loss, Adam optimizer, batch size 64  
- **Evaluation**: Validation/test accuracy, runtime, confusion matrix  
- **Hyperparameter tuning**: Batch size, learning rate, epochs
- **Colab-ready**: Optimized for Google Colab GPU training & evaluation 

---

## Results
| Model               | Validation Acc. | Test Acc. |
|----------------------|-----------------|-----------|
| ResNet50             | **95.7%**       | **92.76%**|
| ResNet152            | 92.5%           | 90.5%     |
| Modified ResNet50    | 91.0%           | 89.16%    |
| Modified ResNet152   | 90.1%           | 89.0%     |

**ResNet50** was the most efficient and accurate model.  
**More depth ≠ better**: ResNet152 added complexity without performance gain.  

For details, see [Report.pdf](Report.pdf).

---

## Installation

### Using Conda
```bash
conda env create -f environment.yml
conda activate resnet-character-classification
```
### Using pip
```bash
pip install -r requirements.txt
```

### Usage 
Run the notebook on Google Colab (GPU recommended):
```bash
jupyter notebook ResNet_classification.ipynb
```

### Project Structure

├── Code └── ResNet_classification.ipynb     # Main notebook

├── Report.pdf                    # Project report

├── environment.yml               # Conda environment

├── requirements.txt              # Python dependencies

└── README.md                     


####  Notes on Running in Colab
When running `esNet_classification.ipynb ` in Google Colab, please consider:

1. **Path setup (Cell 4)**  
   Update the following paths before running:
   - `images_path` → training images  
   - `labels_path` → training labels  
   - `test_images_path` → test images  
   - For each model:  
     - a path for saving predictions  
     - a path for saving model checkpoints  

   On Colab, make sure these directories exist.

2. **Epochs**  
   - In the notebook, the number of epochs is set to `2` (for quick demonstration).  
   - For full training:  
     - **ResNet50 & Modified ResNet50** → 20 epochs  
     - **ResNet152 & Modified ResNet152** → 30 epochs  

3. **Checkpointing**  
   - Model states are saved after each epoch.  
   - If Colab disconnects, simply re-run the notebook → training will resume from the last saved epoch.





