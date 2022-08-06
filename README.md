# Funny-Not-Funny

This project is a retrained iamge classification AI with the purpose of sorting through images and determining whether or not 
an image is concidered an 'animal meme' image or a 'normal portrait' image, hence the name 'Funny Not Funny'.

The Fundementals and Beforehand

This network is a retrained ResNet18 network, specifically trained to detect a funny animal/pet meme images vs a typical human face.
I created my own dataset of 180 total images, 150 training images and 30 verification images.
Of the 150 training images, 75 of them popular pet meme images, and the other 75 normal stock human images.
Of the 30 verification images, 15 of them are again popular pet meme images, and the other 15 normal stock human images.
I then retrained the AI with train.py and the dataset I created and exported the network.

Running the project

1. before running the project make sure you have the Jetson-inference project and docker loaded onto your nano.
2. cd into the Jetson-Inference/python/trianing/classification.
3. make the folders data and models.
4. Inside the data folder, add the Funny_Not_Funny folder to the directory
5. Go back to the classification folder and cd into the models folder.
6. Add the FunnyNotFunny folder into the models folder.
7. Go back into the classification folder
8. Type: NET=models/FunnyNotFunny
9. Type: DATASET=data/Funny_Not_Funny
10. Type: imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/funny/f.jpeg funny.jpeg
11. (optional) Test another image with: imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/boring/b.jpeg boring.jpeg
