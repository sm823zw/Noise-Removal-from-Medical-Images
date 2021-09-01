# Noise-Removal-from-Medical-Images

Image denoising is an important pre-processing step in medical image analysis. Different algorithms have been proposed in past three decades with varying denoising performances. More recently, having outperformed all conventional methods, deep learning based models have shown a great promise.

In this repository, denoising of medical images has been performed using convolutional auto-encoder models. A dental radiography (x-rays) [dataset](http://www-o.ntust.edu.tw/~cweiwang/ISBI2015/challenge1/) have been used in this project. The dataset consists of 400 samples. The samples were resized to smaller dimensions for computational reasons. The original images from the dataset were divided into two sets. 320 of them were used for training and remaining 80 for testing. Due to scarcity of data, data augmentation was perfomed on training images.

For experiments, all the images were corrupted with Gaussian and Poisson noise with varying parameters. The auto-encoder model was then trained keeping the original images as the ground truth. Following that, model performance was evaluated based on structural similarity index (SSIM). The performance of the model was compared to that of traditional median filtering. Following are the results obtained.

| Noise factor 	|        Noise Distribution info   	| SSIM (Noisy Image) 	| SSIM (Auto-encoder Reconstructed Image) 	| SSIM (Median-filtered Image) 	|
|:------------:	|:-------------------------------:	|:------------------:	|:---------------------------------------:	|:----------------------------:	|
|      0.1     	| Gaussian (mean = 0, stddev = 1) 	|       0.4299       	|                  0.8825                 	|            0.7133            	|
|      0.1     	| Gaussian (mean = 1, stddev = 2) 	|        0.224       	|                  0.8068                 	|            0.4683            	|
|      0.2     	| Gaussian (mean = 0, stddev = 1) 	|       0.2321       	|                  0.8029                 	|            0.4844            	|
|      0.2     	| Gaussian (mean = 1, stddev = 2) 	|       0.0986       	|                  0.7022                 	|            0.2652            	|
|      0.5     	| Gaussian (mean = 0, stddev = 1) 	|       0.0789       	|                  0.6625                 	|            0.2146            	|
|      0.2     	|       Poisson (lambda = 1)      	|       0.2518       	|                  0.8428                 	|            0.4284            	|
|      0.2     	|       Poisson (lambda = 5)      	|       0.2159       	|                  0.6118                 	|            0.2350            	|

Auto-encoders performed extremely well as compared to median filtering.
