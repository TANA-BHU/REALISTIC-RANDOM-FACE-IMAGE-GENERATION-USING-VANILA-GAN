# REALISTIC-RANDOM-FACE-IMAGE-GENERATION-USING-VANILA-GAN

In the field of computer vision and artificial intelligence, the creation of fake face images using Generative Adversarial Networks (GANs) has come to be as an exciting and quickly developing field. Fake face image production has received a lot of interest due to the rising need for realistic and high-quality synthetic images, and it has found use in a number of fields including entertainment, computer graphics, and privacy protection. With the development of GANs, the field of image synthesis has undergone a revolutionary change thanks to the availability of a strong framework for producing images with exceptional visual integrity and realism. A discriminator and a generator are the two competing neural networks that make up GANs. While the discriminator network is trained to distinguish between actual and fake images, the generator network tries to create fake images that mimic real photos. These networks learn to enhance their performance iteratively through an adversarial training process, leading to the development of increasingly convincing and undetectable false face images.

**Date collection and Prepossessing:**
The data set for this project was collected from kaggle( https://www.kaggle.com/code/theblackmamba31/generating-fake-faces-using-gan/input?+select=without_mask) containing 10000 HD images.

**Network Architecture:**
The architecture for a Generative Adversarial Network (GAN) typically consists of two main components: the generator and the discriminator. These components work in tandem to train the GAN model.

**Generator Architecture:**
To implement Generative adversarial model we need two sequential model one is Generator and another is Discriminator. The generator will try to generate fake faces from a random noise or latent space whose dimension is 100. The generator is basically a CNN (Convolution Neural Network) having 12 hidden layers where first 6 hidden layer is used for down-sampling and last 6 hidden layers is used for up-sampling and for each hidden layers Leaky Relu is used as the activation function. But for the last layers tanh is used as the activation function . Batch normalization is used in between every pair of hidden layers.

**Discriminator Architecture :**
As the very first layer is the input layers, followed by 5 hidden layers. The first hidden 17layer is a Conv2D layer with 64 filters, a kernel size of 4, and a stride of 2. It uses the 'same' padding and the 'he_normal' kernel initializer. No bias term is used. This layer is followed by a batch normalization layer and a Leaky-ReLU activation function. The next layer is another Conv2D layer with 128 filters, a kernel size of 4, and a stride of 2. It also uses 'same' padding, 'he_normal' kernel initializer, batch normalization, and Leaky-ReLU activation. Next three hidden layers having the filter size of 256,256 and 128 respectably. Before feeding into the dense output layer which have the activation function as sigmoid output is flatten using Flatten layer.

**RESULTS AND DISCUSSION**
The model was implemented in TensorFlow, and training was carried out using Octa core Ryzen 7 CPUs and system RAM is 16GB. Batch-size is 32 and total 10000 RGB images each one is 1024x1024 . ADAM optimizer was employed with a scheduling learning rate of 0.0001, and for the other hyper parameters like and are to default as beta1=0.9, beta2=0.999.

**Result:**
In this section, we present the results of our project on random face image generation using Generative Adversarial Networks (GANs). We evaluate the quality of the generated face images and discuss the outcomes of the training process. The three images in Figures 12, 13, and 14 were produced by the same model respectively after 100, 200, and 5000 epochs.


**Loss Function**
I used 5000 epochs to run this model on a 32x32 picture. The majority of the loss values on the discriminator's graph fall between 0 and 1, which is a really reasonable range for the discriminator. Additionally, we observe that the loss value stays within the same ranges over the course of all 5000 epochs since the discriminator is an un-trainable model. Now, we can detect a rise in our graph's loss value.



