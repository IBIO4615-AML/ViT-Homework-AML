# ViT-Homework-AML

## Installation
Clone this repository and run

```
pip install -r vit_jax/requirements.txt
```
The results from the original ViT paper (https://arxiv.org/abs/2010.11929) have been replicated using the models from this [webpage](gs://vit_models/imagenet21k):

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
