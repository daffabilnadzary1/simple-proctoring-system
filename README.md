# Simple Proctoring System: Cheating-Behavior Detection System

A simple proctoring system prototype developed in Python Notebook to classify numerous types of cheating behavior of a test-taking student.

### Prototype's Methodology:
- A feature engineering step is employed by first resampling the video from 25 FPS to 5 FPS.
- The video used for this is the wearcam video from all the subjects.
- A pre-trained VGG16 model is used as a feature extractor by putting all the extracted frames array to the model.
- Principal Component Analysis (PCA) is used to reduce the complexity of the data by reducing the number of features on the dataset.
- The temporal features of the dataset are captured using a fixed-size sliding window.
- The dataset is trained on two models, XGBClassifier and Temporal Convolutional Network (TCN).
- Each model is evaluated using two evaluation methods, a widely used K-Fold CV and a subject-based evaluation.

### Instructions (Usage):
- The file ```HeyHi Technical Test - Proctoring.ipynb``` contains all the development processes in a form of a Python notebook.
- The notebook can be run sequentially. Some parts can also be skipped if the data already exists (for example the preprocessing and feature engineering step).
- The folder ```Dataset``` contains the preprocessed data as well as the ground truth files. Each preprocessed .csv file contains around 4000-5000 rows with 101 columns.
- All trained models can be found in folder ```Model```. This includes the XGBClassifier model as well as the TCN model.
- To do the training process manually, either download the preprocessed dataset to immediately train or download the ground truth file to do the preprocessing step from the beginning.
- Don't forget to change the path location before running the preprocessing step or the modelling step.

### Known Dependencies:
- [Keras-TCN](https://pypi.org/project/keras-tcn/2.9.3/)
- Tensorflow 2.15.0
- NumPy 1.19.5
- [Scikit-optimize](https://scikit-optimize.github.io/stable/)
