# fishe

This project can detect specific species of fish. 

![add image descrition here](direct image link here)

## The Algorithm

This project uses a resnet18 model that was retrained with 30 different sets of data. Each data set contained a different species of fish. The model was exported after it was trained. The program uses imagenet.py to determine the species of fish.

The dataset can be found here: https://www.kaggle.com/datasets/markdaniellampa/fish-dataset

## Running this project

**Setup**

1. Download the jetson-inference container from github to a jetson-nano: https://github.com/dusty-nv/jetson-inference

2. Change directories into `jetson-inference/python/training/classification/data`

3. Create a directory called "fish"

4. Download the dataset at https://www.kaggle.com/datasets/markdaniellampa/fish-dataset

5. Make a .txt file called "labels.txt" in the "fish" directory and write down the following (in exactly that order)

`Bangus Big_Head_Carp` `Black_Spotted_Barb` `Catfish` `Climbing_Perch` `Fourfinger_Threadfin` `Freshwater_Eel` `Glass_Perchlet` `Goby` `Gold_Fish` `Gourami` `Grass_Carp` `Green_Spotted_Puffer` `Indian_Carp` `IndoPacific_Tarpon` `Jaguar_Gapote` `Janitor_Fish` `Knifefish` `LongSnouted_Pipefish` `Mosquito_Fish` `Mudfish` `Mullet` `Pangasius` `Perch` `Scat_Fish` `Silver_Barb` `Silver_Carp` `Silver_Perch` `Snakehead` `Tenpounder` `Tilapia`

6. Make a new directory called "fish" in jetson-inference/python/training/classification/models


**Execution**

1. Change directories to jetson-inference

2. Type and run `./docker/run.sh` in the terminal

3. Then change directories to `jetson-inference/python/training/classification`

4. Now train the model by running this command in the terminal `python3 train.py --model-dir=models/fish data/fish`

**Note:** This will take approximately 5-6 hours

5. Once done, export the model by running this script

`python3 onnx_export.py --model-dir=models/fish`

6. If you are in the docker container, exit it by pressing ctrl+d

7 .Change directories to `jetson-inference/python/training/classification`

8. In the terminal enter in `NET=models/fish` and `DATASET=data/fish`

9. Then enter in

`imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/fish/malignant8.png output.jpg`

10. If you look in your classification directory there will be a file called output.jpg (or whatever you named the output to be)

11. Display the file to see if there is breast cancer

[View a video explanation here](video link)
