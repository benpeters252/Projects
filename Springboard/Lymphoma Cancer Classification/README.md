

# **Lymphoma Image Classification Using Popular Neural Networks**







##### Problem Statement:



Accurately and automatically classifying lymph node histology images as cancerous or non-cancerous can significantly increase diagnostic throughput and increase accuracy of diagnosis. This could help doctors and patients alike with cancer care.





##### Project Summary:



The PatchCamelon dataset (link below) was used to classify histology slide images as either cancerous or non cancerous using two popular neural networks (ResNet-50 and Virtual Image Transformer (ViT)). Initially the brightness of the images was a concern as some of the brightest and darkest images were either white or black. These were removed by removing the top and bottom 5% of brightest images form the training and test sets. Next, All training images were transformed by flipping and rotating repeatedly 90 degrees (8X images). After these transformations, each model was trained on 960,000 images and then optimized for recall of the cancer images. The final model results are given below in the table. 



Next steps for these models would be to optimize further and to randomize the images further. This could help with model generalization and allow the models to see more features.





##### Final Metrics:





|Metric|ResNet-50|ViT|Winning Model|Priority|Expected for Production|
|-|-|-|-|-|-|
|Recall (Cancer Cells)|90%|97%|ViT|1|>95%|
|Precision (Cancer Cells)|71%|76%|ViT|2|>95%|
|F1 Score|0.79|0.85|ViT|2|>0.95|
|Overall Accuracy|75%|83%|ViT|2|>90%|
|Time per Image|0.318 ms|6.244 ms|ResNet-50|3|<100ms|









##### Model Parameters:

You can download the model parameters for this project in the google doc below as a ZIP file. 

The thresholds for the ResNet-50 model and the ViT model were 0.05 and 0.0001 respectively for cancer image recall.

https://drive.google.com/drive/folders/1mfucCjnyfTsWVTuH297yEIkxB\_Dzyy8L?usp=sharing



##### Notebooks:

https://github.com/benpeters252/Projects/tree/main/Springboard/Captsone%203%20-%20Cancer%20Image%20Classification/Notebooks



##### Data Sources:



PatchCamelon Data:

https://github.com/basveeling/pcam



Original Source for ResNet-50 Model:

https://huggingface.co/microsoft/resnet-50



Original Source for ViT Model:

https://huggingface.co/google/vit-base-patch16-224

