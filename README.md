# Deep Convolutional GAN
Applying [DCGAN](https://github.com/eriklindernoren/PyTorch-GAN#deep-convolutional-gan) to generate some new pokemon's images.
Dataset is taken from  [Pokemon Images Dataset](https://www.kaggle.com/kvpratama/pokemon-images-dataset).

## Images preprocessing

 1. Converting from .PNG to .JPG.
 2. Resizing to 64x64 (can be done directly by model).
 3. Such as original dataset has only 819 items, all images were flipped horizontally and rotated by 3, 5, and 7 degrees clockwise and counterclockwise. It gives us 9828 images.
 
## Model
