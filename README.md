# FashionMNIST_DCGAN_Keras: 
Deep convolutional generative adversarial network for FashionMNIST dataset with Keras and Keras-adversarial.

GAN creates adversarial setup for generator (i.e., convolutional neural network) to produce images with the objective to dupe discriminator (i.e., another convolutional neural network) while the latter trains to distinguish real images from generated ones. 

I pursue the following goals:
1. Testing the capacity of DCGAN to generate images.
2. Making DCGAN implementation less cumbersome thanking to Keras library.

The Keras implementation in ["gan_blob.ipynb"](https://github.com/GSukr/FashionMNIST_DCGAN_Keras/blob/master/gan_blob.ipynb) is similar to ["GAN"](https://colab.research.google.com/github/sakethkaparthi/Apparel-GAN/blob/master/Fashion_MNIST_GAN.ipynb#scrollTo=hz1JhdX7EL5a) though the latter is written with Tensorflow.
To run ["gan_blob.ipynb"](https://github.com/GSukr/FashionMNIST_DCGAN_Keras/blob/master/gan_blob.ipynb) you will need to install keras_adversarial from: [keras-adversarial](https://github.com/bstriner/keras-adversarial/tree/6651cfad771f72521c78a5cc3a23a2313efeaa88). 

![](https://placehold.it/150x40/009955/fff?text=IMPORTANT!) This notebook is not well annotated, please refer to ["Annotated_DCGAN_.ipynb"](https://github.com/GSukr/FashionMNIST_DCGAN_Keras/blob/master/Annotated_DCGAN_.ipynb) for better understanding the code.

The output image at the end of the training is as at Fig 1.
![Fig 1: Images generated at 100th epochs](https://github.com/GSukr/FashionMNIST_DCGAN_Keras/blob/master/images_generated/epoch-099_no_batch.png)

As you can see he DCGAN suffers from so-called **mode dropping**: certain classes are rarely or not generated. As you can see our generated image does not contain any traces of shoes, for example.

I addresed this issues by adding batch normalization in discriminator's network. Batch Normalizations helps overcome the problem of different distribution for each layer's input within training phase. Please refer to ["Annotated_DCGAN_.ipynb"](https://github.com/GSukr/FashionMNIST_DCGAN_Keras/blob/master/Annotated_DCGAN_.ipynb) for the full version of the **notebook with necessary annotation** to follow the code. The updated version produces images as: 
![Fig 2: Images generated at 100th epochs with batch normalization for discriminator](https://github.com/GSukr/FashionMNIST_DCGAN_Keras/blob/master/images_generated/gan_99.png)
