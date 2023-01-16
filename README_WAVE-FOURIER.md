Here my goal was to use an image of a sound wave to classify the type of sound that produced this wave. This seemed like a tricky task because the 
features of differnet classes of waves look relativly the same. I also then compared it to a fourier transform of the wave to see if classifcaiton accuracy
would improve

### Class Distribution

![Unknown-35](https://user-images.githubusercontent.com/47921972/212576559-aebb0fcc-175d-40d0-85aa-24adcc1a07e9.png)


### Acoustic and Acoustic Fourier
![Unknown-36](https://user-images.githubusercontent.com/47921972/212576644-a9174795-17ec-4299-b0e0-097e745a77fe.png)

![Unknown-37](https://user-images.githubusercontent.com/47921972/212576700-86448006-e43f-4425-8513-70753fad5832.png)


### Electronic and Electronic Fourier
![Unknown-38](https://user-images.githubusercontent.com/47921972/212576762-22224a53-db5c-42c6-81ab-ec957c2201b5.png)

![Unknown-39](https://user-images.githubusercontent.com/47921972/212576765-a7ea04da-6f2b-4c0e-bd45-c3b2e6ad2a12.png)

### Synthetic and Sythetic Fourier
![Unknown-40](https://user-images.githubusercontent.com/47921972/212576821-8347c21f-85ea-432e-85b5-fd7e248339e9.png)

![Unknown-41](https://user-images.githubusercontent.com/47921972/212576825-6530ab78-5312-4ea3-9b6d-377b933a5bf9.png)

So here we can kind of see some uniqueness in features between classes, and we can also see the dramatic effect the fourier transform has on the wave. 
Time to run the expirments:

Hyperparameters:
Learning rate .005, 15 epochs, CrossEntropyLoss, SGD optimizer. 

Results: 

### Wave Non Transformed
![Screen Shot 2023-01-15 at 7 56 46 PM](https://user-images.githubusercontent.com/47921972/212577354-38d1050e-ca47-4caf-a079-965ab646ba97.png)


### Fourier
![Screen Shot 2023-01-15 at 7 34 18 PM](https://user-images.githubusercontent.com/47921972/212577034-1cb49e62-a25e-480f-8dab-17b25ce97127.png)



We can first observe that the model is able to classify with a decent accuracy. 
We see also how the fourier transform has a noticable improvement of about 7% over just the wave. 
