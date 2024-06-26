# Comparative Analysis of VGG16 and ResNet50 in Image Classification

  Driven by computer vision technology, image classification has become an important research area.As a branch of image classification, food recognition has a wide range of applications in areas such as health management and nutrition tracking.This study is devoted to exploring the effectiveness of deep learning models in the task of food image classification and comparing the performance of two popular convolutional neural network models, VGG16 and ResNet50.Through careful tuning of hyperparameters, we evaluate the effects of Dropout Rate, Batch Size, Batch Normalization, Weight Decay, Learning Rate, and the number of training rounds on the performance of the models, and analyze the role of different optimizers on the training effectiveness. 

  Our results show that appropriate parameter configurations significantly improve the classification accuracy and generalization ability of the model, where the Adam optimizer exhibits stable performance in a variety of situations due to its adaptive learning rate feature.In addition, this study also explores the application value of early stopping strategy in preventing overfitting. Ultimately, this study not only deepens our understanding of the application of deep learning in food image classification, but also provides insights into the future application of deep learning techniques in a wider range of domains.

# Environmental Dependencies

# Dataset Food-11

  This is a dataset containing 16643 food images grouped in 11 major food categories. The 11 categories are Bread, Dairy product, Dessert, Egg, Fried food, Meat, Noodles/Pasta, Rice, Seafood, Soup, and Vegetable/Fruit. Similar as Food-5K dataset, the whole dataset is divided in three parts: training, validation and evaluation. The same naming convention is used, where ID 0-10 refers to the 11 food categories respectively.
  
  Original dataset can be found [here](https://www.epfl.ch/labs/mmspg/downloads/food-image-datasets/).

## Dropout

  Dropout is an important regularization technique used to reduce overfitting in deep learning models. It forces the network to learn features in a more robust way by randomly setting the output of
some neurons to zero during training. Here, we aim to explore the effect of Dropout rate on food image classification models, especially on the VGG16 network.

  From the experimental results, without Dropout, the model shows a rapid decrease in loss on the training set, but a slower decrease in loss on the validation set, which exhibits some degree of overfitting.

  ![image](https://github.com/Arcadia-Liu/Comparative-Analysis-of-VGG16-and-ResNet50-in-Image-Classification/assets/126369162/60888393-60d1-40e8-aac2-f185c37cc6f2)

  When the Dropout rate is set to 0.3, the loss curves of the model on the training and validation sets are smoother, the overfitting phenomenon is improved, and the accuracy on the validation set is also improved.

  ![image](https://github.com/Arcadia-Liu/Comparative-Analysis-of-VGG16-and-ResNet50-in-Image-Classification/assets/126369162/b6679a61-c163-4b58-9134-0bc2458183a6)

  As the Dropout rate is increased to 0.5, the generalization ability of the model is further enhanced, the loss on the validation set is even lower, and the accuracy is higher.

  ![image](https://github.com/Arcadia-Liu/Comparative-Analysis-of-VGG16-and-ResNet50-in-Image-Classification/assets/126369162/b3b33f24-b50a-40d3-88e0-4339118a3239)

  However, when the Dropout rate is increased to 0.8, while the model still performs well on the validation set, the loss on the training set is higher, suggesting that the model may have lost some of its learning ability due to the high Dropout rate.

  ![image](https://github.com/Arcadia-Liu/Comparative-Analysis-of-VGG16-and-ResNet50-in-Image-Classification/assets/126369162/fec2134c-0466-43a7-8385-c9f6794e90af)

  In summary, a suitable Dropout rate can effectively suppress overfitting and enhance the generalization ability of the model. In our experiments, a Dropout rate setting of 0.5 provided the best generalization performance for the VGG16 model. However, the setting of Dropout rate needs to be adjusted according to the characteristics of the specific problem and dataset, and too high or too low may lead to poor model performance. Therefore, choosing an appropriate Dropout rate is one of the key steps to achieve the best performance of the model.

## Batch Size
  During the training process of a deep learning model, Batch Size is an important hyperparameter that specifies the number of samples used for training in each iteration.The size of the Batch Size
directly affects the convergence speed of the model, memory consumption, and the final performance of the model. Theoretically, a larger Batch Size can provide more stable gradient estimation and thus help accelerate model convergence; however, the actual optimal Batch Size setting needs to be determined experimentally, as too large a Batch Size may lead to insufficient memory and may also affect the quality of the local minima to which the model converges.

  In our experiments, we tried three different Batch sizes: 64, 128, and 256, to observe their effects on the training of the food image classification model.

  ![image](https://github.com/Arcadia-Liu/Comparative-Analysis-of-VGG16-and-ResNet50-in-Image-Classification/assets/126369162/3d51bbbe-98f1-4929-8953-41268dcbad42)

  By comparing the learning curves, we found that the model converges slightly faster with a Batch Size of 256 than with a Batch Size of 128, which may be due to the fact that a larger Batch Size utilizes more data in each update, providing more accurate gradient estimation.

  ![image](https://github.com/Arcadia-Liu/Comparative-Analysis-of-VGG16-and-ResNet50-in-Image-Classification/assets/126369162/9649cb58-7f6b-47b5-942d-fb18bc5a9fa2)

  Meanwhile, the best model obtained on the validation set occurs at the 42nd epoch for a Batch Size of 256, whereas the best model already occurs at the 40th epoch for a Batch Size of 128. This shows that larger Batch Size does not always lead to faster convergence.

  ![image](https://github.com/Arcadia-Liu/Comparative-Analysis-of-VGG16-and-ResNet50-in-Image-Classification/assets/126369162/e34dc7aa-1532-43a0-acf7-5ba228d9b283)

  In terms of training_accuracy (train_acc) and validation_accuracy (valid_acc), the configuration with a Batch Size of 256 slightly outperforms 128 and 64 on the training set, which may be due
to the fact that a larger Batch Size provides more sample variability, allowing the model to learn more generalized features. However, the configuration with a Batch Size of 256 has the highest
accuracy on the validation set, suggesting that this configuration has some advantages in preventing overfitting.

  In conclusion, choosing the right Batch Size has a significant impact on the final performance of the model. A larger Batch Size provides more stable gradient estimation and helps the model learn more generalized features, but also takes into account the limitations of computational resources. In our food image classification task, the Batch Size provides better convergence speed and validation set accuracy for 256, but the optimal Batch Size setting still needs to be flexibly adjusted based on the specific task and available resources.




  








  
