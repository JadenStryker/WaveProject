# WaveProject
CNN, Loss Functions, Decoders/Encoder, GAN, UPSCALING

## Purpose of this project is to explore wave data in relaiton to many deep learning methods such as CNN's AutoEncoders, GAN, and other computational methods


### Project Upscaling using CNN's:
Here my goal was to take a vector describing a sound wave, with features such as pitch, note, instrument, and sample rate and use upscaling methods to turn it into a spectogram of the image. 

For the spectorgrams we have either the default spectogram or the fourier transform of it.

The idea behind this is that the features of the vector imply some shape to the spectogram of the wave. Thus we want to use the shape and local information ability of a CNN to upscale the vector, and then output a spectogram similar to that the origonally was described by the vector. 
THis is a non conventional task for a CNN because CNN's are acustomed to learning features of an image, and not an upscaled vector. They also look for certain real world features, like textures and shapes, only shapes are now the output. This gets into the in-explainability of a CNN, but it will be an interesting task to play around with. 

The first issue that arose is the density of a spectogram, Very little of the wave is occupied in the output spectogram. This means an insane loss, and a highly specific task for the network. Initially the loss was around 10e8, for MSE. This immidiatly set all the weights to zero, and even after training the model produced zero for every value. So I scaled the loss. This was still producing zero because of this density idea. So I thought to encourage the model to produce more values by changing the loss funciton to be decreased based on the average of the values. Thus the model would not be incentivized to move all weights to zero. This fixed the problem. However the output was still junk, but at least not zero. It seems the computational complexity for upscaling doesnt allow great learning in this task. 

I still want to try a distance from proper density based aproach, where loss punished the farther away from the average density of actual spectograms

![Screen Shot 2023-01-12 at 4 59 07 PM](https://user-images.githubusercontent.com/47921972/212190173-487a8ba0-d81a-4c3f-9013-8b4f2e8c7897.png)
#### This is for non scaled, and standard MSE
![Screen Shot 2023-01-12 at 4 55 22 PM](https://user-images.githubusercontent.com/47921972/212189549-3bb8e6d0-9db7-4780-ad19-bf4fd24222c7.png)
#### This is for scaled and loss function encouraging higher values in output - y_pred Loss : 40
![Screen Shot 2023-01-12 at 5 54 13 PM](https://user-images.githubusercontent.com/47921972/212198548-667d1537-c785-4678-ab2e-157591b55420.png)
#### This is the loss for scaled and distance from 'normal' loss, Loss : 122
![Screen Shot 2023-01-12 at 5 00 01 PM](https://user-images.githubusercontent.com/47921972/212190309-b706945b-d818-4389-9dd3-6b20a6117b9c.png)
#### This is y_true
