# Funny-Not-Funny

This project is a retrained iamge classification AI with the purpose of sorting through images and determining whether or not 
an image is concidered an 'animal meme' image or a 'normal portrait' image, hence the name 'Funny Not Funny'.

# The Fundementals and Beforehand

This network is a retrained ResNet18 network, specifically trained to detect a funny animal/pet meme images vs a typical human face.
I created my own dataset of 180 total images, 150 training images and 30 verification images.
Of the 150 training images, 75 of them popular pet meme images, and the other 75 normal stock human images.
Of the 30 verification images, 15 of them are again popular pet meme images, and the other 15 normal stock human images.
I then retrained the AI with train.py and the dataset I created and exported the network.

# Running the project

1. before running the project make sure you have the [Jetson-inference](https://github.com/dusty-nv/jetson-inference) project and imagenet.py loaded onto your nano. Please refer to the Jetson Inference project when setting up nano.
2. cd into the Jetson-Inference/python/trianing/classification.
3. clone the repository.
4. Type: NET=Funny-Not-Funny/models/FunnyNotFunny
5. Type: DATASET=Funny-Not-Funny/data/Funny_Not_Funny
6. Type: imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/image.jpg
