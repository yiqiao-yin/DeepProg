# DeepProg

<p align='center'>
<img width="588" alt="Example Mask Table" src="https://user-images.githubusercontent.com/103869590/175452211-fb04d0da-ab88-4514-ab3d-73cc782aa09e.PNG">
<img width="588" alt="Example Crop Table" src="https://user-images.githubusercontent.com/103869590/175452210-31e44b71-034f-4e31-8d4a-bc88b578a426.PNG">
<img width="588" alt="DenseNet" src="https://user-images.githubusercontent.com/103869590/179291908-def12ab5-6b3e-498d-9436-d2a57828effc.png">
</p>

Contains a module for functions that build and evaluate a U-Net Model which is a modified auto-encoder image-to-image architecture that includes skip connections from encoder to decoder layers with matching input dimensions to retain features from the encoded image. The model is designed for image segmentation and produces a mask based off x-ray data. The model is used with lung x-rays to segment out lungs, brain scans to segment out brain tumors, and pictures of a room to segment out a human figure. With the COVID-QU-Ex chest x-ray dataset for lung segmentation, it is able to achieve 98% accuracy with a wide range of 3,4,5 encoding block of Conv2D and MaxPooling and BatchNormalization + 1 latent layer without pooling and the mirrored number of decoding layers that do Conv2DTranspose for deconvolution and UpScaling to reverse MaxPooling making 7,9,11 layers with doubling filters/kernels in each encoding block from 16,32,64,80 that double with each block like in a traditional CNN and then half with each decoding block.

The initial source is designed from [this github](https://github.com/LLeon360/UNetBiomedicalDiagnosis).

## Open Source Colab

Colab: Unet Training: https://colab.research.google.com/drive/1q8k_JOL2-EkIIpuX2x3EcqEAtwWfuBoB#scrollTo=sV328lJpNOMD 
Unet Result + CNN + GradCAM Heatmap: https://colab.research.google.com/drive/1hGpYr7w37-9qHvYaFKWLQKPytmldCT0S#scrollTo=uWeiAf8ybw-j
