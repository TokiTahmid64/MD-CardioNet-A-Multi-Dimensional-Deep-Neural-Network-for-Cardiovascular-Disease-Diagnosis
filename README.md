# MD-CardioNet-A-Multi-Dimensional-Deep-Neural-Network-for-Cardiovascular-Disease-Diagnosis-from-Electrocardiogram
This is the official implementation of the paper "MD-CardioNet: A Multi-Dimensional Deep Neural Network for Cardiovascular Disease Diagnosis from Electrocardiogram". Necessary codes and datasets are provoded.

Download the Dataset used for training and testing from the following link:
https://drive.google.com/drive/folders/1PAAna696ia29RdcxxULYY2mYpDXhRLXN?usp=sharing


# To Run and Make Prediction using the Model:

1. Download the Dataset
2. Download the model.json and model.h5 files that containes the trained weights of the model
3. Run the following script to load the model:

    ```
    from keras.models import model_from_json
    json_file = open('../model.json', 'r')
    loaded_model_json = json_file.read()
    json_file.close()
    loaded_model = model_from_json(loaded_model_json)

    loaded_model.load_weights("../model.h5")
    print("Loaded model from disk")

    ```
    
4. Run the following script to make prediction with any data from the downloaded dataset:
    
    ```
    Y_pred=loaded_model.predict('Any input data with shape (12,1000)')
    y_pred=np.argmax(Y_pred,axis=1)
    
    ```
    Where,
    0:        SB (Sinus Bradycardia)
    
    1:        SR (Sinus Rhythm)
    
    2:        trychardia
    
    3:        AFIB (Atrial fibrilation)
    
    4:        AF (Atrial flatter)
    
    5:        SA (Sinus irragularity)
