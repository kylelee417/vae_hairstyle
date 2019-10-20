# vae_hairstyle
* [Variational Autoencoder(VAE)- Hairstyle V.01]: This is my introductory Variational Autoencoder (VAE) model project to build a basic vae model to randomly generate different hairstyle after training the model with various front-view men hairstyle dataset. The main goal was to observe extraordinary hairstyle by sampling random latent attributes from the latent space. Hopefully, those new images of hairstyle could inspire designers or people to try a new style and individual experiencing hair loss process could preview themselves with various hairstyling after some treatment for future applications. Keras with TensorFlow backend was used to build the VAE model and an autoencoder model as well on Google Colab Jupyter notebook base. Several limitations were encountered when those models were built:

1. very limited train and test data - each dataset was created using **google_images_download** and images were directly saved on mounted google drive. very small dataset (~500 train set and ~90 test) was used to train the full vae model after mannually eliminating variables (i.e. facial orientation, faces with glasses, etc.).

2. low pixel size - 96 x 96 was used in this project. Pixels lower or higher than 96 made it very difficult building the model with deeper layers or the training was not efficient. 
3. very underfitted model - combination of #1 and #2 resulted in 53% and 61% loss performance of the autoencoder and vae models. 

For future direction to this project would be training the model with a larger dataset would give a better outcome.  After the fine training, we could manually locate the latent vectors to find specific styles so that the user can apply different hairstyles on the same face input.

<p align="center">
  <img src="VAE/testset.png" width="70%" class="center">

The autoencoder model was able to catch general outlines of the original image with a 53% loss. VAE model was supposed to predict input images as much as close to the input image using a trained latent vector.  

<p align="center">
  <img src="VAE/newimg.png" width="70%" class="center">

Compared to the autoencoder, the vae model was able to generate a new image regardless of noise or bald input images.  

Loss Plots:
<p align="center">
  <img src="VAE/loss.png" width="80%" class="center">

As you can see, both models were highly under fitted after 300 epochs. The autoencoder was somewhat showing a trend to be less under fitted after further epochs, however, it is not an efficient process. For the VAE model, better optimizations in hyperparameters are required as it did not show improvements during the whole training process.
  
<p align="center">
  <img src="VAE/generated.png" width="60%" class="center">  


Now let's look at the newly generated 10 x 10 images from the decoder model in 2 latent dimensions. Even though there was a high 62% loss, there were noticeable changes in the hair portion as the sampling points shift to the right.  
For more information understanding theories behind VAE, refer to a well summarized [Jeremy Jordan][11]'s blog. 
</p>
