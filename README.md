# GANdetection
GANdetection is an application that can distinguish faces of real people from faces created through GANs.


#### Abstract
*Generative models, such as GANs (generative adversarial networks), are now able to produce images of such high quality that even humans can be fooled. Various methods and models have been proposed in recent years, but many of them are unable to generalise to architectures and datasets from unknown sources. In this work, the question was asked whether it would be possible to construct a universal detector that could distinguish real images of human faces from GAN-generated images. To achieve this goal, models were built using the dataset of a single adversarial generative network and a dataset of real images. It is shown that using images of a GAN with a different variation of the 'truncation trick' significantly increases the generalisation capability of the models. The results obtained suggest that many GANs to date share the same defects that can be detected to enable the distinction of real images from synthetic images.*


## Experimentation
The training, validation and evaluation datasets were pre-processed with [face detect](https://github.com/francescovolpe/GANdetection/blob/main/Face_detect.ipynb) and then [resized to 160x160](https://github.com/francescovolpe/GANdetection/blob/main/Resize_images.ipynb).
Composition of the training and validation dataset.
| Fake        | #F | Real           | #R |
| ------------- |-------------|-------------|-------------|
| StyleGAN  (CAHQ) 0.5    | 18.777 | CAHQ | 26.824 |
| StyleGAN  (CAHQ) 0.7    | 2.682 | 
| StyleGAN  (CAHQ) 1.0    | 5.365 | 

## Dataset
The training, validation and evaluation datasets are available from the following repository [repository](https://github.com/francescovolpe/Dataset-GANdetection)

## Model accuracy
| Fake | StyleGAN (CAHQ) | Glow | ProGAN | StyleGAN 2 (FFHQ) | DiscoFaceGAN | FaceAPP DFFD |
| ------------- |-------------|-------------|-------------|------------- |-------------|-------------|
|  |99.6 | 56.2 | 99.1 | 98.8 | 99.9 | 99.4 |

| Real | CAHQ | FFHQ | CelebA | LFW | UTKFace |
| ------------- |-------------|-------------|-------------|------------- |------------- |
| | 100 | 2.9 | 100 | 100 | 99.7 |


## Test

1. [Download the model](https://drive.google.com/file/d/1o7ApG_QclqaDDFuP0Rp2YefTuxCeJHsc/view?usp=sharing)
2. Preprocess the dataset to be evaluated with [face-detect](https://github.com/francescovolpe/GANdetection/blob/main/Face_detect.ipynb)
3. [Resize](https://github.com/francescovolpe/GANdetection/blob/main/Resize_images.ipynb) to 160x160 (bicubic) the dataset pre-processed with face detect
4. Run the [Test.ipynb](https://github.com/francescovolpe/GANdetection/blob/main/Test.ipynb) notebook modifying the path of the dataset to be evaluated


## Libraries used
We recommend the use of [Goole Colab](https://colab.research.google.com/)
- tensorflow 2.4.1
- keras 2.4.0
- numpy 1.19.5
- matplotlib 3.2.2
- face-recognition 1.2.3
- pillow 8.0.0

## Problems viewing notebooks
If you experience problems viewing notebooks due to rendering, you can use [nbviewer](https://nbviewer.jupyter.org/)
