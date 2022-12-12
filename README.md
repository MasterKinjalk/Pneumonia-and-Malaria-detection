<h1> Pneumonia and Malaria detection from X-ray and Cell Images </h1>

## Sample Output

<h3> Pneumonia Detected<h3>
<p align="center">

<img src="https://user-images.githubusercontent.com/60870318/207118900-0293aaf0-5a56-48be-ac36-c82e85bdabc8.png" alt="Pneumonia Positive" width=80%/>

</p>

<h3> Pneumonia Not Detected<h3>
<p align="center">

<img src="https://user-images.githubusercontent.com/60870318/207118922-07d0268a-cac0-48c3-b3d9-d46c7560fb1b.png" alt="Pneumonia Negative" width=80%/>

</p>

<h3> Malaria Detected<h3>

<p align="center">

<img src="https://user-images.githubusercontent.com/60870318/207118943-e5b89868-2281-424c-86d8-3de30b194cdb.png" alt="Malaria Postive" width=80%/>

</p>

<h3> Malaria Not Detected<h3>

<p align="center">

<img src="https://user-images.githubusercontent.com/60870318/207118951-f03a7a2a-5831-447f-8688-12fdd672f827.png" alt="Malaria Negative" width=80%/>

</p>

## The Models

### Pneumonia Model

- The [Chest X-Ray Images (Pneumonia)](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia) dataset from [Kaggle](https://www.kaggle.com/) has been used to train this model.
- This model has been trained to identify 2 classes (Positive or negative for Pneumonia) using transfer learning on the InceptionV3 model till layer ‘mixed7’, followed by a Dense layer with 512 nodes (RelU), and a sigmoid layer with 1 output node using Keras with Tensorflow backend. 
- It was trained using the RMSprop optimizer with a batch size of 64. Input size of the images were (150, 150, 3). The images were rescaled before training. ([trainPneumonia.ipynb](https://github.com/Data-Science-Community-SRM/disease-predictor/blob/master/trainPneumonia.ipynb))
- The final trained model resulted in an accuracy of 85.2% on the test set with 777 images.
- Each image is resized to 150x150 and then normalized before feeding into the network to make a prediction. 

### Malaria Model

- The [Malaria Cell Images Dataset](https://www.kaggle.com/iarunava/cell-images-for-detecting-malaria) dataset from [Kaggle](https://www.kaggle.com/) has been used to train this model.
- It was trained using the public Kaggle notebook [Detecting Malaria (val accuracy > 97%)](https://www.kaggle.com/harshel7/detecting-malaria-val-accuracy-97).

## The Flask Web Application

- The Web Application has been built with Flask in the backend and HTML and Bootstrap for the frontend.
- Respective images (.jpg, .jpeg, .png) can be uploaded to get predictions for Pneumonia and Malaria.
- Functionality for preventing upload of file of any format other than .jpg, .jpeg and .png has been included.
- Sample images are included in the [Sample images](https://github.com/Data-Science-Community-SRM/disease-predictor/tree/master/Sample%20images) folder.

### Execution

- The prerequisites for running the Flask Application are included in the requirements.txt file.
- To run the application:
```
export FLASK_APP=run.py
export FLASK_ENV=development
flask run
```
