# Dashtoon_Assignment
# Requirements to run the notebook:
For smooth working of this notebook please use these settings. Create a new virtual environment and install these dependencies in it.
1. Python == 3.7.6
2. Torch == 1.5.1
3. Torchvision == 0.6.0a0+35d732a
4. Numpy == 1.18.1
5. PIL == 5.4.1
6. tqdm == 4.45.0
7. Matplotlib == 3.2.1
8. OpenCV == 4.2.0.34
9. CUDA Version == 10.1


# The loss function used are:
Content Loss: The content cost function is making sure that the content present in the content image is captured in the generated image. As CNNs capture information about content in the higher levels, where the lower levels are more focused on individual pixel values, we use the top-most CNN layer to define the content loss function.
Style Loss: To extract the style information from the VGG network, we use all the layers of the CNN. Furthermore, style information is measured as the amount of correlation present between features maps in a given layer. Next, a loss is defined as the difference of correlation present between the feature maps computed by the generated image and the style image.
We are taking the sum of both losses as the main loss to make sure that both style and content are leveraged together.

# Architecture used:
Training a style transfer model requires two networks: a pre-trained feature extractor and a transfer network. The pre-trained feature extractor is used to avoid having to retrain the whole training data to regain features. It’s usefulness arises from the curious tendency for individual layers of deep convolutional neural networks trained for image classification to specialize in understanding specific features of an image.The pre-trained model enables us to compare the content and style of two images, but it doesn't actually help us create the stylized image. That’s the job of a second neural network, which we’ll call the transfer network. The transfer network is an image translation network that takes one image as input and outputs another image. Transfer networks typically have an encode-decoder architecture. At the beginning of training, one or more style images are run through the pre-trained feature extractor, and the outputs at various style layers are saved for later comparison. Content images are then fed into the system. Each content image passes through the pre-trained feature extractor, where outputs at various content layers are saved. The content image then passes through the transfer network, which outputs a stylized image. The stylized image is also run through the feature extractor, and outputs at both the content and style layers are saved.

# Evaluation Metrics:
Structural similarity index(ssim): This metric was used to track the content feature of the transformed images in order to preserve the content of the photo.
Limitations:
Unavailability of Online Resources(GPU): Was not able to run the model for various iterations/epochs due to unavailability of GPU’s.
Not Proper Evaluation Metric for Styling feature.
The Transfer Network is not properly trained compared to other transfer learning used models hence results were less than expected.

# Potential Improvements:
The Transfer Network could be trained on more data and iterations to give better results.
A better loss function could be devised to compensate between style loss and content loss.
Other optimisation techniques such as cross_validation, callback etc could be used to further improve performance.



