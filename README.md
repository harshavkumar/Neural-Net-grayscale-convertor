# Neural-Net-grayscale-convertor
A neural net to convert RGB image into a grayscale image

## Dependencies:

- OpenCV -> 3.4.3
- Tensorflow -> 1.14
- Numpy -> 1.16.4
- Glob
- Google Colab

## How to run:

 1. Download Dataset from [here](http://vision.stanford.edu/aditya86/ImageNetDogs/images.tar). After downloading the dataset, you will see a folder “Images” having various subfolders “n02085620-Chihuahua, n02085782-Japanese_spaniel, n02085936-Maltese_dog” having dog breed images.

 2. Make Directories for training i.e. “color” and “grayscale” by using above using dataset as dog_path1,2,3…

 3. Create testing Directory “color_test” of color images, so that it can fit to our tensor network/ graph of (128,128,3)

 4. Training our model on training dataset and storing model for further use to specific folder “Model”

 5. Creating numpy array of giving testing dataset so that we can run over neural net to create Grayscale image.

 6. Restoring model and feeding testing image numpy array and saving converted grayscale to generated Directory “generated_images”.


## Approach:

Autoencoders is used as neural net because they designed in such a way that they don’t learn to copy the input to output perfectly instead they are restricted in ways that they learn to copy approximately.

Autoencoder is used instead of traditional neural network model because they don’t take into account that a signal could be a composition of other signals. On the other hand, autoencoder with convolutional trait can use convolution operator to exploit this observation. They learn to extract the useful set of signals and then try to reconstruct the input. They learn the optimal filters that minimize the reconstruction error instead of manually engineering convolutional filters.

Usually, to train the autoencoder the input image and the target image (what the autoencoder must learn to reconstruct) is the same but for our task, the input image is in RGB format and the target image is in grayscale format. This forces the autoencoder to learn the function to convert an RGB image to a grayscale image.
