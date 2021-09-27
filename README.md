# CIFAR-10
In this project, I built a neural network of my own design to evaluate the CIFAR-10 dataset.

To meet the requirements for this project, I needed to achieve an accuracy greater than 45%, and greater than 70% to beat Detectocorp's algorithm (Detectocorp was a fictional AI classification supplier).

## Loading the Dataset
In order to create a viable solution, I started by loading the dataset with various image transformations first. For the training and validation datasets, this was a 15 degree random image rotation, followed by a random crop and a random flip. I did this to artificially enlarge and augment the dataset, as well as create a network that could generalise well.  Obviously all datasets were then converted to PyTorch Tensors and normalised. 

I created the validation dataset as a subset of the training data by simply sampling a random 20% of the training data, so in all I had 3 datasets.

## Exploring the Dataset
While a function to display 5 images from the data was provided, this did not work on my datasets and required a bit of fine-tuning. This involved replicating the normalisation and then re-indenting a few loops. While I tried resizing the images back to 32 x 32 pixels, this didn't lead to any visual improvements in displaying them (i.e. they stayed blurry), so I left them at 224 x 224.

## Building and Running the Neural Network
I had used VGG-11 in a previous project and was keen to try something different, either another VGG with added layers (I tried VGG-16), or a completely different architecture, such as a Resnet. I'd read that Resnet is an improvement on VGG in terms of speed, so I wanted to make my own comparisons. 

While my Resnet-18 network was definitely faster, the accuracy was only around 48%. Retraining with differing hyperparameters (eg I used learning rates, epochs and optimizers), resulted in only incremental changes - this prompted me to move back and try VGG-16. Again accuracy was low at slightly less than 50%, and as I was running out of time on the GPU I finally tried VGG-11 again. This simple CNN hit the accuracy out of the park as it had in a previous project, I was able to immediately see accuracy of around 80%. 

While I then tried using Adam instead of SGD as an optimiser, this actually led to the accuracy going down again to between 40-50%. So again it seems that a low complexity model with an older optimiser does the trick for this dataset. Running the network to 12 epochs in the end resulted in an accuracy of 85%, and if I had additional time on the GPU I would have tried running to 18 or 20 as I think 90% is definitely possible.

