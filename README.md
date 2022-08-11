# Deep Convolutional Generative Adversarial Networks for Celebrity Face

Celebrity face Generator by DCGAN from scratch. 

Structure and hyperparameters from paper [Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks](https://arxiv.org/pdf/1511.06434.pdf).

### Progress
![Progress GIF](/assets/Progress.gif)

### Discriminator Net Structure
![Discriminator Net Structure image](/assets/DiscriminatorNet.png)

### Generator Net Structure
![Generator Net Structure image](/assets/GeneratorNet.png)


## Data Summary

### Train images
![Train image](/assets/TrainImages.png)

- .jpg format
- 64 px x 64 px (Height x Width)


| Class | Train Number |
| --- | --- |
| **Total** | 202599 |

Data from [Large-scale CelebFaces Attributes (CelebA) Dataset](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html).


Data Structure(default in notebook):

root\
--> data\
----> all images dir\
------> 001.jpg\
------> 002.jpg\
------> 003.jpg\


## Results

Loss by Binary CrossEntropy Loss.  Data normalized in 3 color channels. (Mean: [0.5, 0.5, 0.5], Std: [0.5, 0.5, 0.5])


Model | NetD Loss | NetG Loss | NetD on real Acc | NetD on fake Acc | Train Time | 
--- | --- | --- | --- |--- | --- |
First 5 epochs | 0.4938 | 4.3929 | 0.9179 | 0.3017 | 179m 27s |
Second 3 epochs | 0.4621 | 4.4151 | 0.9323 | 0.2549 | 108m 55s |


Loss and acc are all in last epoch, last batch.

Trained on CPU.


### Loss on first 5 epochs
![Loss image](/assets/Loss.png)

### Progress after first train
![Progress after first train image](/assets/ProgressEnd.png)

### Progress after second train
![Progress after second train image](/assets/Progress2End.png)



## Usage/Examples

### Random Generated Image 1
![Random Generated Image 1](/assets/Random1.png)

### Random Generated Image 2
![Random Generated Image 2](/assets/Random2.png)

### Random Generated Image 3
![Random Generated Image 3](/assets/Random3.png)

### Random Generated Image 4
![Random Generated Image 4](/assets/Random4.png)

### Random Generated Image 5
![Random Generated Image 5](/assets/Random5.png)


1. First 5 epoch named Netxxx.pt/.pth  

2. Second 3 epoch named Netxxx_2.pt/.pth  

3. Steps to use (copy steps at the end of notebook):

 - Reconstruct Generator Model by structure shown above.
 - Load model weights by pytorch API.
 - Generate random noise with lantent vector size(100).
 - Treat noise as regular tensor.
   - Transpose channels from front to the end.
   - Denormalize it ([0.5, 0.5, 0.5], [0.5, 0.5, 0.5])
   - Plot with plot library.



## Library Versions

- python: `3.10.4`
- torch: `1.12.0`
- torchvision: `0.13.0`
- numpy: `1.23.1`
- matplotlib: `3.5.2`
