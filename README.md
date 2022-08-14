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

The classifier is trained to predict the binary attributes based on the CelebA dataset in the following order
```python
classifier_labels = ['Arched_Eyebrows', 'Attractive', 'Bags_Under_Eyes', 'Bald',
       'Bangs', 'Big_Lips', 'Big_Nose', 'Black_Hair', 'Blond_Hair',
       'Blurry', 'Brown_Hair', 'Bushy_Eyebrows', 'Chubby', 'Double_Chin',
       'Eyeglasses', 'Goatee', 'Gray_Hair', 'Heavy_Makeup',
       'High_Cheekbones', 'Male', 'Mouth_Slightly_Open', 'Mustache',
       'Narrow_Eyes', 'No_Beard', 'Oval_Face', 'Pale_Skin', 'Pointy_Nose',
       'Receding_Hairline', 'Rosy_Cheeks', 'Sideburns', 'Smiling',
       'Straight_Hair', 'Wavy_Hair', 'Wearing_Earrings', 'Wearing_Hat',
       'Wearing_Lipstick', 'Wearing_Necklace', 'Wearing_Necktie', 'Young']
```

In the training process you can choose the indices (zero-indexed) of any subset of these labels as `--subset_labels`
The default subset of labels are set as `[25,11,17,28,27,34,16,3]` which means the following labels:
Pale_Skin, Bushy_Eyebrows, Heavy_Makeup, Rosy_Cheeks, Receding_Hairline, Wearing_Hat, Gray_Hair, Bald.

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