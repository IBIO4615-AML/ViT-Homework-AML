# ViT-Homework-AML

*For this homework you will need to hand in a report (.pdf) with the required information. 

The paper [An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale](https://arxiv.org/abs/2010.11929) shows that Transformers applied directly to image patches and pre-trained on large datasets work really well on image recognition tasks. The results from this paper using various arquitectures and multiple datasets are in the table below. 

| model	| dataset	| dropout=0.0	| dropout=0.1 |
| --- | --- | --- | --- |
|R50+ViT-B_16 |	cifar10 |	98.72%, 3.9h (A100), tb.dev	| 98.94%, 10.1h (V100), tb.dev |
|R50+ViT-B_16	| cifar100 |	90.88%, 4.1h (A100), tb.dev	| 92.30%, 10.1h (V100), tb.dev |
|R50+ViT-B_16	|imagenet2012|	83.72%, 9.9h (A100), tb.dev|	85.08%, 24.2h (V100), tb.dev|
|ViT-B_16|	cifar10|	99.02%, 2.2h (A100), tb.dev	|98.76%, 7.8h (V100), tb.dev|
|ViT-B_16|	cifar100|	92.06%, 2.2h (A100), tb.dev|	91.92%, 7.8h (V100), tb.dev|
|ViT-B_16	|imagenet2012|	84.53%, 6.5h (A100), tb.dev|	84.12%, 19.3h (V100), tb.dev|
|ViT-B_32	|cifar10	|98.88%, 0.8h (A100), tb.dev	|98.75%, 1.8h (V100), tb.dev|
|ViT-B_32	|cifar100	|92.31%, 0.8h (A100), tb.dev	|92.05%, 1.8h (V100), tb.dev|
|ViT-B_32	|imagenet2012|	81.66%, 3.3h (A100), tb.dev|	81.31%, 4.9h (V100), tb.dev|
|ViT-L_16	|cifar10	|99.13%, 6.9h (A100), tb.dev	|99.14%, 24.7h (V100), tb.dev|
|ViT-L_16	|cifar100	|92.91%, 7.1h (A100), tb.dev	|93.22%, 24.4h (V100), tb.dev|
|ViT-L_16	|imagenet2012|	84.47%, 16.8h (A100), tb.dev|	85.05%, 59.7h (V100), tb.dev|
|ViT-L_32	|cifar10	|99.06%, 1.9h (A100), tb.dev	|99.09%, 6.1h (V100), tb.dev|
|ViT-L_32	|cifar100	|93.29%, 1.9h (A100), tb.dev	|93.34%, 6.2h (V100), tb.dev|
|ViT-L_32	|imagenet2012|	81.89%, 7.5h (A100), tb.dev|	81.13%, 15.0h (V100), tb.dev|

## First Task (1 point):

Recreate the results from the ViT-B_16 architecture with the cifar10 dataset. Attach evidence from your results in your report.

```
pip install -r requirements.txt

# imagenet21k pre-train
wget https://storage.googleapis.com/vit_models/imagenet21k/ViT-B_16.npz

#Run train.py
python train.py --name cifar10-100_500 --dataset cifar10 --model_type ViT-B_16 --pretrained_dir ViT-B_16.npz
```

*Note: The default batch size is 512. When GPU memory is insufficient, you can proceed with training by adjusting the value of --gradient_accumulation_steps.

## Second task:

Open the modeling.py file in the models folder. Explain in your own words *whats* happening between lines 83 to 91 (Find the #Start and #Finish comments) and *why*. Explain the relevance of the operations.  

## Third Task:

As you already know, self-attention is essential in ViT. The attention map for the input image can be visualized through the attention score of self-attention. Open the ViT_Visualize.py file. 

###### Part A (0.5 points):

Read the code and answer the questions/instructions included in the code. 

###### Part B (1.5 points):

Choose 6 images of 6 different categories (ej. golden retriever, piano, person, etc) from the internet. The image must be .jpg and you need to copy the image address and include it in the corresponding part of the code. Visualize the attention maps of the 6 images. Attach a subplot which includes the original image and the attention map obtained. 

###### Part C ():

Choose 3 images from the previous exercise and visualize the attention maps from the first, middle and last layer. Attach a subplot with the original image and the corresponding 3 attention maps. Write a brief description and explanation about the differences between layers. 

## Hand Ins
Report (.pdf)
ViT_Visualize.py completed

