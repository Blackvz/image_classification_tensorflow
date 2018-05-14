# Image Classification with tensorflow

1. Start a tensorflow docker container and mount tf_files into the container
```
docker run -it -v ~/Projects/image_classification_tensorflow/tf_files:/tf_files gcr.io/tensorflow/tensorflow:latest-devel
```

2. cd /tensorflow; git pull;

# Guess if image contains trained search patterns
```
python /tf_files/src/label_image.py "/tf_files/images/test-image.jpg"
```

## You want to create own training data?

1. Put images into /images

2. Create new training data with:

```
python /tensorflow/tensorflow/examples/image_retraining/retrain.py \
--bottleneck_dir=/tf_files/bottlenecks \
--how_many_training_steps 500 \
--model_dir=/tf_files/inception \
--output_graph=/tf_files/retrained_graph.pb \
--output_labels=/tf_files/retrained_labels.txt \
--image_dir /tf_files/images/
```
