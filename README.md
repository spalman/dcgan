# Deep Convolutional GAN
Applying [DCGAN](https://github.com/eriklindernoren/PyTorch-GAN#deep-convolutional-gan) to generate some new pokemon's images.
Dataset is taken from  [Pokemon Images Dataset](https://www.kaggle.com/kvpratama/pokemon-images-dataset).

## Images preprocessing

 1. Converting from .PNG to .JPG.
 2. Resizing to 64x64 (can be done directly by model).
 3. Such as original dataset has only 819 items, all images were flipped horizontally and rotated by 3, 5, and 7 degrees clockwise and counterclockwise. It gives us 9828 images.
 
## Model
DCGAN consists of two networks:
 
 - Discriminator *D*: *D* is CNN that applies a lot of filters to extract various features from an image. The discriminator network trained to discriminate between the original and generated image.
 - Generator *G*: generates an image from random noize *z*. *G* is represented by CNN that upsample the input. The convolution over this net will produce a larger input for the next stage.

~~Space for computational graph image~~
## Results
Unfortunately my ancient PC(i5-2500 +GTX 560) can't handle training process with CUDA. So, here is some results after going thru 3200 batches on CPU (~20 epochs).
![giphy!](https://gph.is/g/Z8kPpda)
~~Will also try to run it on GCP when there will be available compute engines with GPU.~~

## Run train process

	python3 dcgan.py [OPTIONS]

> '--train_dir', type=str, default='mnist', help='path to training data'
'--n_epochs', type=int, default=200, help='number of epochs of training'
'--batch_size', type=int, default=64, help='size of the batches'
'--lr', type=float, default=0.0002, help='adam: learning rate'
'--b1', type=float, default=0.5, help='adam: decay of first order momentum of gradient'
'--b2', type=float, default=0.999, help='adam: decay of first order momentum of gradient'
'--n_cpu', type=int, default=8, help='number of cpu threads to use during batch generation'
'--latent_dim', type=int, default=100, help='dimensionality of the latent space'
'--img_size', type=int, default=32, help='size of each image dimension'
'--channels', type=int, default=1, help='number of image channels'
'--sample_interval', type=int, default=400, help='interval between image sampling'
'--save_epoch', type=int, default=10, help='interval between model checkpoints'
