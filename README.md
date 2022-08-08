## Explaining Image Classifiers Using Contrastive Counterfactuals in Generative Latent Spaces

Pytorch implementation for the paper https://arxiv.org/pdf/2206.05257.pdf

## Clone this repo
```bash
git clone https://github.com/KamranAlipour/Contrastive-Counterfactuals-with-GAN.git
cd Contrastive-Counterfactuals-with-GAN/
```

## Download weights
```bash
pip install gdown
mkdir -p GAN_models/pretrained/generators/StyleGAN2
gdown https://drive.google.com/uc?id=1vxrymegJOfE1PydPO9cvvQvNzpmKnakA -O GAN_models/pretrained/generators/StyleGAN2/stylegan2-ffhq-config-f.pt
mkdir -p classifier_weights/
gdown https://drive.google.com/uc?id=1zHmxPVPAMuEosPGuTU2CNVJ6VwC0NEJ9 -O classifier_weights/celebA_MultiLabels_vgg11_classifier.pt
```

## Train the shift predictor model
```bash
python train.py
```

## Citation
If you use this code for your research, please cite our paper: 
```
@article{alipour2022explaining,
  title={Explaining Image Classifiers Using Contrastive Counterfactuals in Generative Latent Spaces},
  author={Alipour, Kamran and Lahiri, Aditya and Adeli, Ehsan and Salimi, Babak and Pazzani, Michael},
  journal={arXiv preprint arXiv:2206.05257},
  year={2022}
}
```