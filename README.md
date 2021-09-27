# CIFAR-10
In this project, I built a neural network of my own design to evaluate the CIFAR-10 dataset.

To meet the requirements for this project, I needed to achieve an accuracy greater than 45%, and greater than 70% to beat Detectocorp's algorithm (Detectocorp was a fictional AI classification supplier).

In order to create a viable solution, I started by loading the dataset with various image transformations first. For the training and validation datasets, this was a 15 degree random image rotation, followed by a random crop and a random flip. I did this to artificially enlarge the dataset, as well as create a network that could generalise well.  Obviously all datasets were then converted to PyTorch Tensors and normalised. 

I created the validation dataset as a subset of the training data by simply sampling a random 20% of the training data, so in all I had 3 datasets as normal.

## Exploring the Dataset
