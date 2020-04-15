# Table of Content

<ol>
  <li>Introduction</li>
  <li>Kaggle's PetFinder Dataset</li>
  <li>Models</li>
   <ol>
     <li>Table classification</li>
     <li>NLP classification</li>
     <li>Image classification</li>
     <li>Ensemble classification</li>
   </ol>
</ol>

# Introduction
For the project in the courses Artificial Intelligence II and Data Driven Transformation taught during our Master in Business Analytics at Esade, we chose Kaggle's PetFinder competition.

PetFinder is a Malaysian company that is a platform for selling and buying pets, mostly dogs and cats. The company wants to help its users to find an appropriate buyer quicker. Therefore, the challenge is to predict pet's adoption speed.

# Kaggle's PetFinder Dataset
The PetFinder dataset can be downloaded from their Kaggle page: https://www.kaggle.com/c/petfinder-adoption-prediction/data

We only use the "train" and "train_images" folder.

The variable to predict "Adoption Speed" contains five classes:
<ul>
  <li>0 = Pet adopted within 24 hours of listing</li>
  <li>1 = Pet adopted within 7 days of listing</li>
  <li>2 = Pet adopted within 30 days of listing</li>
  <li>3 = Pet adopted within 90 days of listing</li>
  <li>4 = Pet not adopted after 90 days of listing</li>
 </ul>

# Models
We developed three classifiers: a table classifier, a language (nlp) classifier, and an image classifier. 

A test set was created from the train.csv to check our accuracy. This was done in the "create_image_datasets.ipynb" notebook. Also, changed adoption speed form five classes to four classes by replacing class 0 with 1, as the number of pets with class 0 is very small.

## Table classification

Table classification was done with a trial and error methodology. We tried out 10 different classification algorithms with 3 different models in order to compare the results and the accuracy achieved:
<ol>
  <li>Basic cleaned model.ipynb - notebook of the first model that uses the cleaned dataset from Trifacta</li>
  <li>Second model.ipynb - notebook that comprises a feature engineered model (rescuer_count_ID, state_GDP, etc.) and factorizes categorical variables</li>
  <li>Third model.ipynb - notebook with the extensive feature engineered model which binarizes each column and creates subcategories</li>
</ol>


## NLP classification
NLP classification was done using fastai's text library. 

Two notebooks were used for NLP classification:
<ol>
  <li>create_image_datasets.ipynb - notebook to create training set.</li>
  <li>model_language.ipynb - notebook that runs the nlp classifier.</li>
</ol>

## Image classification
Image classification was done using fastai's vision library. Applied three models: resnet34, densenet121, and vgg19.

Two notebooks were used for image classification:
<ol>
  <li>create_image_datasets.ipynb - notebook to create .csv files that will be used by the fastai library to identify the relevant images for training.</li>
  <li>model_image.ipynb - notebook that runs the image classifier.</li>
</ol>

## Ensemble classification
Ensemble classification combined the table classifier, nlp classifier as well as the image classifiers (resnet34, densenet121 and vgg19) to predict the adoption speed. 

Three notebooks were used for ensemble classification:
<ol>
  <li>copy_test_images_new_folder.ipynb - notebook that creates a new folder with the test images, subset of the "train_images" folder which was not trained on.</li>
  <li>ensemble_prediction.ipynb - notebook that runs the ensemble classifier.</li>
  <li>accuracy_submissions.ipynb - notebook to score our predictions against the test set.</li>
</ol>
