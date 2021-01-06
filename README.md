# TransferLearning_ImageClassification_Keras
Building an Image Classifier using Transfer Learning (ResNet50 model) in Keras on Intel Image Classification Dataset.

Transfer Learning - a method where a model trained on a dataset is used on another task. Here we generally resue more Generic Knowledge Layers(Low level layers) and fewer Task-Specific Layers(Top lovel layers). During the training the low level layers are frozen and newer task specific layers are modified.

## Dataset
- The dataset is downloaded from [Intel Image Classification Dataset](https://www.kaggle.com/puneet6060/intel-image-classification).
- The dataset contains 6 categories and we have used 2 categories - 'Forest' and 'Glacier'.
> Folder structure
  - data
    - train
      - forest
      - glacier
    - val
      - forest
      - glacier

## Optional
Rename the file names by appending folder names at the beginning i.e forest/2205.jpg -> forest/forest_2205.jpg
  ```
  import os

  for root, dirs, files in os.walk("Parent"):
    if not files:
        continue
    prefix = os.path.basename(root)
    for f in files:
        os.rename(os.path.join(root, f), os.path.join(root, "{}_{}".format(prefix, f)))
  ```
Source: [stackoverflow](https://stackoverflow.com/questions/38948774/python-append-folder-name-to-filenames-in-all-sub-folders)

## Clone Project
git clone https://github.com/Krishna2709/TransferLearning_ImageClassification_Keras.git

## Install required libraries and packages
- tensorflow
- numpy
- math
- matplotlib

## Steps
a. Model Building
1. Load the required packages
2. Load and augment the data
3. Define and train the model
4. Prediction on example images

b. Analysis
1. Load the data and predict their categories
2. Accuracy of the prediction
3. Analyze the model predictions

``` 
get_images_with_sorted_probabilities-
  arguments: predictions, get_highest_probability:True/Flase, label:category, number_of_items:int(number of images), only_false_predictions:True/False

display-
  arguments: probability values from the query, message to display
```

## Analyzing model results
Looking at model predictions give an intuition how well the model is working and areas where the model need to be tuned.
1. Which images are we most confident about being forest or glacier?
2. Which images are we least confident about being forest or glacier?
3. Which images have incorrect predictions inspite of being highly confident?

## To-do
- [x] Add model.h5
- [x] Add steps in building the project.
- [x] Describe the functions used in the code.

## Credits & Resources
[Practical Deep Learning for Cloud, Mobile & Edge - Anirudh Koul, Siddha Ganju & Meher Kasam](https://www.oreilly.com/library/view/practical-deep-learning/9781492034858/)
