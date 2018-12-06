# Convert-keras-to-tf-and-deploy-using-tfserving
Keras to TF and Deploy via tfserving

 - Train and save Keras model
 - Convert Keras model to TensorFlow SavedModel
 - Create tensorflow/serving container to serve model
 - Test service
 
 1.Train and save Keras model
 
 This part is done on Kaggle, [notebook link](https://www.kaggle.com/wangmo/self-driving-cars-road-segmentation-task).
 
 2.Convert Keras model to TensorFlow SavedModel
 
 Code in notebook: keras-to-tf.ipynb
 
 3.Create tensorflow/serving container to serve model
 
 '''
 docker run -d --name tf-serving --mount type=bind,\
   source=/path/to/exported_model,\
   target=/model/road_seg \
   -e MODEL_NAME=road_seg tensorflow/serving  
 '''
 4.Test service
 Notebook: test_client.ipynb