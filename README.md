# ✨ Fake-Face-Generation-Using-GAN✨ 

**INTRODUCTION :**
Generative Adversarial Networks (GANs) are generative models. They are uses unsupervised technique to generate new things. GAN models learns pattern in input data in such a way that they can generate new sample which resemble with the input data. The main aim of generative adversarial network is to match generated distribution with the original data distribution.

GANs are an exciting and rapidly changing field, delivering generative models ability to generate realistic examples across a range of problem domains, most notably in image-to-image translation tasks such as translating photos of summer to winter or day to night,coloring images and in generating fake photos that even human cannot categorized as fake image. This site uses GAN to generate fake human faces which are similar to real human.

### Flow chart of the fake face generation:
![image](https://user-images.githubusercontent.com/108206047/197688343-9168c700-56bd-42b9-a92a-16ac01eabd91.png)

**COMPONENTS OF GAN:**

**Generator :** Generator are neural network that learns to generate data which resemble with the input distribution. The generator model take fixed dimension random vector from Gaussian distribution as input and generate the sample out of it which resemble with input.

**Discriminator :** Discriminator are simple neural network that distinguish fake and real data.The discriminator model takes an example from the domain as input (real or generated) and predicts a binary class label of real or fake.

Generative adversarial networks are based on a game theoretic scenario in which the generator network must compete against an adversary. The generator network directly produces samples. Its adversary, the discriminator network, attempts to distinguish between samples drawn from the training data and samples drawn from the generator.

**Working of GAN**
![image](https://user-images.githubusercontent.com/108206047/197688420-81e605b9-f724-480a-9f6a-ab7f1d291e6b.png)

First of all we take batch of random vector from the Gaussian distribution and generate fake image out of it using generator. Since generator isn't trained so generated image donot resemble with the real input distribution. We take batches of image from the input distribution along with generated fake images and fed it to discriminator so that it learns to distinguish between real and fake images. Now, after training discriminator, we take the batch of images that generator generated and fed them through discriminator again (here we donot fed real images), discriminator will provide an output probabilities, these values are then compared with the probability that the generator should generated (ie 1), error is calculated and backpropagated through the generator and the weight are updated. This above process is repeated until generated images resemble with the input distribution.

####**APPLICATIONS OF GAN:**

1.   Generating Fake faces
2.   Generating examples for image Datasets
3.   Face aging
4.   Super Resolution
5.   Image to Image Translation
6.  Photos to Emojis
7.  Text to Image Tranlation
8.  Generate cartoon characters


**Generator:**

Here, I have defined generator network. It take random vector from normal distribution as input. This random vector is passed through dense layer and is reshaped and is finally fed through Convolution layers.

The final output layer of Generator generate 12 by 12 by 10 image. The final layer of generator uses hyperbolic tangent as activation to squash the value in between -1 and 1. Generator model looks like simple autoencoder model, where input data is downsampled first and is finally upsampled .

**Discriminator:**

Here, discriminator model take 12 by 12 by 10 image that can be real or generated. This input image is downsampled using Convolution layer and is finally flattened and is fed to single neuron so that it can distinguish real and fake image. Since, final layer uses sigmoid function as activation, it output value in between 0 and 1. Here value greater than 0.5 refers to real and less than 0.5 refers to fake image. The output of discriminator is used in training of generator.

**data set link:**

processed-celeba-small dataset zip file: "https://drive.google.com/file/d/1-9fjO6Mfpb8BzijuDdQf-NML8aYseJNH/view?usp=sharing"
