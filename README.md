# ViT-Homework-AML

*For this homework you will need to hand in a report (.pdf) with the required information. 

The paper [An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale](https://arxiv.org/abs/2010.11929) shows that Transformers applied directly to image patches and pre-trained on large datasets work really well on image recognition tasks. The results from this paper using various arquitectures and multiple datasets are in the table below. 

| model	| dataset	| dropout=0.1 |
| --- | --- | --- |
|R50+ViT-B_16 |	cifar10 |	98.94%, 10.1h (V100), tb.dev |
|R50+ViT-B_16	| cifar100 |	92.30%, 10.1h (V100), tb.dev |
|R50+ViT-B_16	|imagenet2012|	85.08%, 24.2h (V100), tb.dev|
|ViT-B_16|	cifar10| 98.76%, 7.8h (V100), tb.dev|
|ViT-B_16|	cifar100|	91.92%, 7.8h (V100), tb.dev|
|ViT-B_16	|imagenet2012|	84.12%, 19.3h (V100), tb.dev|
|ViT-B_32	|cifar10	| 98.75%, 1.8h (V100), tb.dev|
|ViT-B_32	|cifar100	| 92.05%, 1.8h (V100), tb.dev|
|ViT-B_32	|imagenet2012| 81.31%, 4.9h (V100), tb.dev|
|ViT-L_16	|cifar10	| 99.14%, 24.7h (V100), tb.dev|
|ViT-L_16	|cifar100	| 93.22%, 24.4h (V100), tb.dev|
|ViT-L_16	|imagenet2012 |	85.05%, 59.7h (V100), tb.dev|
|ViT-L_32	|cifar10	|99.09%, 6.1h (V100), tb.dev|
|ViT-L_32	|cifar100	|93.34%, 6.2h (V100), tb.dev|
|ViT-L_32	|imagenet2012| 81.13%, 15.0h (V100), tb.dev|

## First Task (1 point):

Recreate the results from the ViT-B_16 architecture with the cifar10 dataset. Attach evidence from your results in your report.

```
#Previously install the requirements
$ pip install -r requirements.txt

# Download the imagenet21k pre-train model
$ wget https://storage.googleapis.com/vit_models/imagenet21k/ViT-B_16.npz

#Run train.py
$ python train.py --name cifar10-100_500 --dataset cifar10 --model_type ViT-B_16 --pretrained_dir ViT-B_16.npz
```
Use [Automatic Mixed Precision(Amp)](https://nvidia.github.io/apex/amp.html) to reduce memory usage and train faster by setting --fp16_opt_level to O2 (--fp16 --fp16_opt_level O2).

*Note: Set train batch size and number of steps to 1000, otherwise it will take about 50 hours to run. 
*Note: When GPU memory is insufficient, you can proceed with training by adjusting the value of --gradient_accumulation_steps to 10.

## Second task (1 point):

Open the modeling.py file in the models folder. Explain in your own words *whats* happening between lines 83 to 91 (Find the #Start and #Finish comments) and *why*. Explain the relevance of the operations.  

## Third Task (3 points):

As you already know, self-attention is essential in ViT. The attention map for the input image can be visualized through the attention score of self-attention. Open the ViT_Visualize.py file. 

###### Part A (1 point):

Read the code and answer the questions/instructions included in the code. 

###### Part B (1 point):

Choose 6 images of 6 different categories (ej. golden retriever, piano, person, etc) from the internet. 

**Specifications:**
1. The image must be .jpg
2. Copy the image address and include it in the corresponding part of the code

Visualize the attention maps of the 6 images. Attach a subplot which includes the original images and the attention maps obtained. 

###### Part C (1 point):

Choose 3 images from the previous exercise and visualize the attention maps from the _**first, middle and last layer**_. Attach a subplot with the original images and the corresponding 3 attention maps. Write a brief description and explanation about the differences between layers. 

## Hand In
Attach the required files to your homework repository. 
1. Report (.pdf)
2. ViT_Visualize.py completed

