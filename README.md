Table of contents
1. Abstract
2. Dataset
3. Images preparation
4. Models used for transfer learning
5. Model training
6. Comparision between models
7. Summary
</br>

<p>
1. Abstract</br>
The goal of the project is to build model to predict weather the lungs are healthy or not. I decided to use transfer learning from popular models trained on big datasets and choose the one, which is best in classification chest x-rays. The x-rays are in gray scale, therefore I duplicated data to three layers to make it possible to use models trained on RGB images.
</p>

<p>
2. Dataset</br>
Dataset consist of train, test and validation data. Each set is divided into two classes: </br>
"Normal" - healthy lungs</br>
"Pneumonia" - unhealthy lungs</br>
The training dataset consist of 1341 images of healthy lungs and 3875 images of unhealthy ones.

You can find more information about dataset at the link</br>
The data source: https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia
</p>

<p>
3. Images preparation </br>
Images where loaded as RGB images to duplicate gray-scale on each rgb layer. To make model quality better there has been used image augmentation while loading training data - the images where randomly changed by sheering,zooming or changing brigtness. The images where also rescaled to 200x200 resolution. The test data where not augmented, only rescaled. 
</p>


<p>
4. Models used for transfer learning
Five models where choosen for this project:
  <ul>
  <li>VGG16</li>
  <li>VGG19</li>
  <li>InceptionV3</li>
  <li>Xception</li>
  <li>ResNet50</li>
  </ul>
  Initial weight where loaded from models and then frozen. There were added few layers on top which were trainable and were perforing final classification.
</p>

<p>
5. Model training </br>
Models where trained by monitoring val_loss. Initial number of epoch where high to stop the model by EarlyStopping - only when there is no significant improvement betweeen epochs. Best weights were saved.
</p>

<p>
6. Comparision between models</br>
Different models used for transfer learing were compared basing on val_accuracy and val_loss in table.</br>
Table with comparison of different models
</p>

<p>
7. Summary</br>
(Assesing of best solution)
</p>
