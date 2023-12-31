# midterm-GAN
by, K. Thach

## Introduction 

Super Resolution GAN (SRGAN) is a deep learning architecture that uses a combination of GANs and convolutional neural networks (CNNs) to generate high-resolution images from low-resolution images. The idea behind SRGAN is to train a generator network to create high-resolution images that are as close as possible to the real high-resolution images, and a discriminator network that is trained to distinguish between the generated high-resolution images and real high-resolution images. The training process involves feeding low-resolution images to the generator, which then generates a high-resolution image. The discriminator then evaluates the generated high-resolution image and provides feedback to the generator to improve the quality of the generated image. The generator and discriminator networks are trained iteratively until the generated images are of sufficient quality. Super Resolution GAN has many practical applications, such as in medical imaging, satellite imagery, and video processing. It can help to enhance the quality of low-resolution images, making them more useful for analysis and decision-making.

## Steps:

Part 1

* Train a binary classifier (called A) on the dataset using transfer learning (exactly like Assignment 1). The images should be downscaled to 128x128

Part 2

* Next, train the SRGAN to generate 128x128 images. Each image of the training is downscaled to 32x32.
* Train the SRGAN for at least 150 epochs
* Show some examples of scaled images in JNB

Part 3 

* Utilize the images generated by SRGAN in order to train a new model (called B)
* Divide the dataset into 70% training and 30% testing
* Apply normalization and image transformation, and demonstrate some of the transformed samples
* Compare the performance of both models using different metrics such as F1, Accuracy, AUC
* Since there is limited time to use Google Colab GPU every 12 hours, save your models after each n epoch

## Implementation of Steps

To implement this code locally begin with the `start.py`. This file will help install the `virtual environment` as `.env` and all dependencies required. 

1. `midterm-GAN.ipynb` is the notebook that corresponds with **Part 1** 
    This notebook trains a binary classifier using the cat vs. dog dataset. The dataset is expected to be local to the script. Ensure all paths are altered and organized similarly to sucessfully train the model. See notebook in [Assignment 1] for a few functions to help organize images into folders and utilize the `.flow_from_dataframe` image generator approach. 

2. `SRResNet.ipynb` is used to train the SRGAN model. The model is trained using the Cat vs. Dog dataset, which is imported via the `td_load()` function. The dataset structure is altered as such: . The training is expected to run for 150 epochs / iterations. This notebook corresponds with **Part 2**.

3. `compare_models.ipynb` is used to train *Model B*. Model B utilizes the SRGAN images to train a binary classifier. This training will use the same model structure in `Model A`. After training the model, the performance of `Model A` is compared to `Model B`. This notebook corresponds with **Part 3**.

### Actual Colab scripts, training and outputs

Click on the link below to view the full training in Google CoLab, resources and all outputs.
See [Drive](https://drive.google.com/drive/folders/10ctH-vA0Qny44CdsPiq4PfWyIhdpwddL?usp=sharing)



## Resources

1. https://arxiv.org/pdf/1609.04802.pdf 
2. https://www.kaggle.com/code/ahmadjaved097/using-transfer-learning-to-classify-cats-dogs
3. https://medium.com/analytics-vidhya/implementing-srresnet-srgan-super-resolution-with-tensorflow-89900d2ec9b2
4. https://manishdhakal.medium.com/super-resolution-with-gan-and-keras-srgan-4bd810d214b6