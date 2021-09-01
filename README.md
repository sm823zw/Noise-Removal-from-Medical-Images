# Noise-Removal-from-Medical-Images

Image denoising is an important pre-processing step in medical image analysis. Different algorithms have been proposed in past three decades with varying denoising performances. More recently, having outperformed all conventional methods, deep learning based models have shown a great promise.

In this repository, denoising of medical images have been performed using convolutional auto-encoder models. A dental radiography (x-rays) [dataset](http://www-o.ntust.edu.tw/~cweiwang/ISBI2015/challenge1/) have been used in this project. The dataset consists of 400 samples. The samples were resized to smaller dimensions for computational reasons. The original images from the dataset were divided into two sets. 320 of them were used for training and remaining 80 for testing. Due to scarcity of data, data augmentation was perfomed on training images.

For experiments, all the images were corrupted with Gaussian and Poisson noise with varying parameters. The auto-encoder model was then trained keeping the original images as the ground truth. Following that, model performance was evaluated based on structural similarity index (SSIM). The performance of the model was compared to that of traditional median filtering.

Auto-encoders performed extremely well as compared to median filtering.
