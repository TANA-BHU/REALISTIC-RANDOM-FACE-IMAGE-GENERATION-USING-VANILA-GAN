# Realistic Random Face Image generation using Vanilla GAN.

In the field of computer vision and artificial intelligence, the creation of fake face images using Generative Adversarial Networks (GANs) has come to be an exciting and quickly developing field. Fake face image production has received a lot of interest due to the rising need for realistic and high-quality synthetic images, and it has found use in several fields including entertainment, computer graphics, and privacy protection. With the development of GANs, image synthesis has undergone a revolutionary change thanks to the availability of a strong framework for producing images with exceptional visual integrity and realism. A discriminator and a generator are the two competing neural networks that make up GANs. While the discriminator network is trained to distinguish between actual and fake images, the generator network tries to create fake images that mimic real photos. These networks learn to enhance their performance iteratively through an adversarial training process, leading to the development of increasingly convincing and undetectable false face images.

![image](https://github.com/TANA-BHU/REALISTIC-RANDOM-FACE-IMAGE-GENERATION-USING-VANILA-GAN/assets/103022959/46c016e5-4a85-47b3-9949-3f584ac3e9fc)


***Date collection:***
The data set for this project was collected from Kaggle ( https://www.kaggle.com/code/theblackmamba31/generating-fake-faces-using-gan/input?+select=without_mask) containing 10000 HD images.

![Screenshot from 2023-09-21 17-10-43](https://github.com/TANA-BHU/REALISTIC-RANDOM-FACE-IMAGE-GENERATION-USING-VANILA-GAN/assets/103022959/da39c56a-7d77-4bff-8440-7e12e475ee9f)

**Network Architecture:**
The architecture for a Generative Adversarial Network (GAN) typically consists of two main components: the generator and the discriminator. These components work in tandem to train the GAN model.

**Generator Architecture:**
To implement the Generative adversarial model we need two sequential models one is a Generator and another is a Discriminator. The generator will try to generate fake faces from a random noise or latent space whose dimension is 100. The generator is a CNN (Convolution Neural Network) with 12 hidden layers. The first 6 hidden layers are used for down-sampling, the last 6 hidden layers are used for up-sampling, and each hidden layer Leaky Relu is used as the activation function. But for the last layers, tanh is used as the activation function. Batch normalization is used in between every pair of hidden layers.

![Screenshot from 2023-09-21 17-30-41](https://github.com/TANA-BHU/REALISTIC-RANDOM-FACE-IMAGE-GENERATION-USING-VANILA-GAN/assets/103022959/5f0c05c0-151a-4e93-949e-9064c99a6de5)

**Discriminator Architecture:**
The very first layer is the input layer, followed by 5 hidden layers. The first hidden 17layer is a Conv2D layer with 64 filters, a kernel size of 4, and a stride of 2. It uses the 'same' padding and the 'he_normal' kernel initializer. No biased term is used. This layer is followed by a batch normalization layer and a Leaky-ReLU activation function. The next layer is another Conv2D layer with 128 filters, a kernel size of 4, and a stride of 2. It also uses 'same' padding, 'he_normal' kernel initializer, batch normalization, and Leaky-ReLU activation. The next three hidden layers have the filter size of 256,256 and 128 respectively. Before feeding into the dense output layer with the activation function as sigmoid output is flattened using a flattened layer.

![image](https://github.com/TANA-BHU/REALISTIC-RANDOM-FACE-IMAGE-GENERATION-USING-VANILA-GAN/assets/103022959/d93ce3c3-bfe9-46bd-a52c-8e57224fa725)

**Results and Discussion:**
The model was implemented in TensorFlow, and training was carried out using Octa core Ryzen 7 CPUs and system RAM is 16GB. Batch-size is 32 and the total 10000 RGB images each one is 1024x1024. ADAM optimizer was employed with a scheduling learning rate of 0.0001, and for the other hyperparameters like and are to default as beta1=0.9, beta2=0.999.

**Result:**
In this section, we present the results of our project on random face image generation using Generative Adversarial Networks (GANs). We evaluate the quality of the generated face images and discuss the outcomes of the training process. The three images in Figures 12, 13, and 14 were produced by the same model respectively after 100, 200, and 5000 epochs.

![Screenshot from 2023-09-21 17-21-48](https://github.com/TANA-BHU/REALISTIC-RANDOM-FACE-IMAGE-GENERATION-USING-VANILA-GAN/assets/103022959/e5fd3b26-1feb-44d8-8b87-896d963bccc7)

![Screenshot from 2023-09-21 17-27-06](https://github.com/TANA-BHU/REALISTIC-RANDOM-FACE-IMAGE-GENERATION-USING-VANILA-GAN/assets/103022959/9c99b468-3bb1-4721-85d4-52424a3b4f59)

![Screenshot from 2023-09-21 17-27-42](https://github.com/TANA-BHU/REALISTIC-RANDOM-FACE-IMAGE-GENERATION-USING-VANILA-GAN/assets/103022959/5c187a70-2ebb-47cc-b914-a1d7b339895f)

![Screenshot from 2023-09-21 17-28-12](https://github.com/TANA-BHU/REALISTIC-RANDOM-FACE-IMAGE-GENERATION-USING-VANILA-GAN/assets/103022959/10402cbf-a4c8-4709-aae4-f0943cfe7e1d)

![Screenshot from 2023-09-21 17-28-55](https://github.com/TANA-BHU/REALISTIC-RANDOM-FACE-IMAGE-GENERATION-USING-VANILA-GAN/assets/103022959/f3bbab77-1236-4169-b1cc-e822f48305b2) 


**Loss Function:**
I used 5000 epochs to run this model on a 32x32 picture. The majority of the loss values on the discriminator's graph fall between 0 and 1, which is a reasonable range for the discriminator. Additionally, we observe that the loss value stays within the same ranges throughout all 5000 epochs since the discriminator is an un-trainable model. Now, we can detect a rise in our graph's loss value.

![Screenshot from 2023-09-21 17-29-57](https://github.com/TANA-BHU/REALISTIC-RANDOM-FACE-IMAGE-GENERATION-USING-VANILA-GAN/assets/103022959/2f770a9d-44c0-4a2e-98c1-499f9ba9fb62)



