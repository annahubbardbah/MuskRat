# MuskRat
Booz Allen Hamilton Summer Games 2022 Project 
## Downloading the backend (backend_anna)
mkdir Muskrat -
cd Muskrat

git init
git remote add origin https://github.com/annahubbardbah/MuskRat.git
git fetch
git checkout backend_anna
## Dataset 
1. Download the dataset using the below link
https://www.kaggle.com/datasets/yihaopuah/deep-fake-images/download?datasetVersionNumber=1
2. UNIZP and make sure the path is readable from './dataset/archive/'
## Sequential_model.ipynb
Displays the Architecture of a three layer sequential model using the keras API and TensorFlow 
## read_in_dataset_and_format.ipynb
Reads Training data from './dataset/archive/train' (looping through real_image and fake_image)
outputs X.pickle and y.pickle (both python lists)
X.pickle: Grayscale image data represented as a Matrix
y.pickle: Binary Classification of the corresponding image data 'real_image' == 0 & 'fake_image' == 1
Reads Validation data from './dataset/archive/val' 
X_val.pickle
y_val.pickle
Defines Python Functions 
### def read_data(directory_name, x_list):
Function returns list of [image data, class]  within given directory 
## from_pickle_load_then_predict.ipynb
Loads in *pickle files as proof of concept 
*.pickle data used to train models 
Loads in *.h5 files - these represent saved models
All *.h5 models are variations of the same model architecture trained on a different quarter of the 2GB Dataset
Reads in a Test Set to use as input for model predictions
Reads images from './test_internet/fake_image' and './test_internet/real_image'
Defines Python Functions 
### def accuracy_results():
Displays the following metrics associated within a testing image dataset
most_freq is the most frequent classification per image of all 5 models
total pred is a list with all 5 model predictions in a sublist
true_class is the true classification of the image
ACCURACY = total correct num of predictions / total predictions
### def display_img_with_data(): 
Displays the image in the testing dataset './test_internet' stored in the model_data array 
Displays the corresponding metrics for that input image 
Example:
<Figure>

True Classification: 
real_image

Aggregate Classification: 
real_image

Individual Model(s) Classification: 
Model 1: real_image
Model 2: real_image
Model 3: real_image
Model 4: fake_image
Model 5: real_image