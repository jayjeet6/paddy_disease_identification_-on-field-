﻿# caption_generation_flickr8k
Objective:
This study aims to develop a robust image classification method for accurately categorizing paddy images into 10 specific disease classes prevalent in on-field conditions. The classes include bacterial leaf blight, bacterial leaf streak, bacterial panicle blight, blast, brown spot, dead heart, downy mildew, hispa, normal, and tungro. Given the intricacies of on-field data and the challenges in distinguishing diseases visually, our objective is to leverage advanced deep learning techniques to enhance the precision and reliability of disease classification.
Overview of the Method's Approach:
Our approach involves refining and integrating three pre-trained models—VGG16, MobileNetV2, and ResNet—by introducing modifications to the top layers. VGG16 is known for its deep architecture with 16 weight layers, MobileNetV2 is recognized for its lightweight design suitable for mobile devices, and ResNet is renowned for its residual learning framework that facilitates the training of very deep networks.
The modifications applied to the top layers of each pre-trained model are tailored to enhance their ability to capture subtle disease symptoms, variations in lighting conditions, and diverse backgrounds encountered in on-field scenarios. Fine-tuning is utilized to optimize the models for improved disease classification performance while maintaining the knowledge gained from their original pre-training datasets.

Modifications or enhancements to existing algorithms:
In our quest to enhance the classification accuracy of paddy diseases in on-field images, we leverage established techniques and models while introducing modifications to address specific challenges. Initially, employing pre-trained models (VGG16, MobileNetV2, and ResNet) with a single dense layer yielded suboptimal validation accuracy (around 50-55%). To overcome this limitation, we incorporated additional layers at the top of the pre-trained models, aiming to extract more nuanced features and improve classification performance.
Architectural Enhancements:
1.	Flatten Layer:
•	Purpose: Transforms output into a flat vector for compatibility with dense layers.
2.	Dense Layers (1024, 512, 128, 64):
•	Purpose: Extracts high-level features and abstract representations, enhancing the model's capacity for capturing intricate patterns.
•	NOTE(I HAVE ALSO Used AVERAGEMAXPOOLING2D layer but this is not giving me good accuracy approx 4 to 8 % less in every model but in this case model train very fast)
3.	Batch Normalization:
•	Purpose: Stabilizes and accelerates training by normalizing layer activations, mitigating internal covariate shift, and improving convergence.
4.	Dropout Layers:
•	Purpose: Introduces regularization to prevent overfitting, enhancing generalization by randomly dropping units during training.
Classification Layer:
•	Dense Layer (10 with Softmax Activation):
•	Purpose: Executes the final classification, producing probability distributions over the 10 disease classes.
Data Preprocessing:
•	Utilization of the pre-trained model's built-in preprocess input function ensures proper formatting and normalization of input data, aligning with the model's requirements.
•	Augmentation of the data through flipping enhances model generalization by introducing variations to the input images.
By incorporating these enhancements, we not only leverage the knowledge encoded in pre-trained models but also tailor them to the intricacies of on-field paddy disease classification. This approach aims to strike a balance between leveraging existing techniques and introducing modifications to optimize model performance for the specific challenges posed by the classification task.

Evaluation of Model Performance on Testing Dataset:
In assessing the classification performance of the proposed models on the testing dataset, the following accuracies were achieved:
VGG16: 86.91%
The VGG16-based model demonstrated a testing accuracy of 86.91%, showcasing its effectiveness in classifying paddy diseases from on-field images.
MobileNet: 87.36%
The MobileNet-based model exhibited a testing accuracy of 87.36%, indicating its competence in the given classification task.
ResNet: 89.97%
Notably, the ResNet-based model outperformed the other architectures, achieving a testing accuracy of 89.97%. This superior accuracy suggests the effectiveness of ResNet in capturing intricate patterns associated with various paddy diseases in on-field images.
These results highlight the varying degrees of success among the tested models, with ResNet emerging as the most promising model for accurate paddy disease classification in the specified on-field conditions.
