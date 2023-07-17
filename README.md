# DARKFFHQ
A Benchmark for face hallucination in low-light scenarios

## Overall
Face hallucination in low-light environments is an extremely challenging task due to the significant loss of facial structure and facial texture information. 
We construct a low-light face hallucination dataset DARKFFHQ-4000 based on the face dataset [FFHQ](https://github.com/NVlabs/ffhq-dataset) as a benchmark for low-light face hallucination task.
This dataset will provide researchers with a standardized and uniform benchmark for training and evaluation.

## Dataset generation
We select 4000 face images from the FFHQ dataset and downsample the HR face images using the Bicubic degradation model with scale factors of 4 and 8, resulting in 4000 face images with 64 $\times$ 64 pixels and 4000 face images with 32 $\times$ 32 pixels. These two sets of images are used as the LR face image. After that, we synthesize low-light LR face images based on the LR face images. 
We randomly select parameters $\alpha$, $\beta$, and $\gamma$ that are used to control contrast, brightness, and gamma correction in three well-designed ranges during the synthesis of each image.
The process of generating low-light LR face images can be formulated as ${LR}_{low}(x,y) = \left(\frac{\alpha \times LR{(x,y)} + \beta}{255}\right)^{\gamma} \times 255$.
More details are provided in [Learning to Hallucinate Face in the Dark](https://ieeexplore.ieee.org/document/10180077).

<div align=center><img src="datasetsample.png" width="100%"></img></div>
