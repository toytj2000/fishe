# fishe

This project can detect specific species of fish. 

![add image descrition here](direct image link here)

## The Algorithm

Add an explanation of the algorithm and how it works. Make sure to include details about how the code works, what it depends on, and any other relevant info. Add images or other descriptions for your project here. 

## Running this project

1. Download the jetson-inference container from github to a jetson-nano: https://github.com/dusty-nv/jetson-inference

2. Change directories into `jetson-inference/python/training/classification/data`

3. Create a directory called "fish"

4. Download the dataset at https://www.kaggle.com/datasets/markdaniellampa/fish-dataset

5. Make a .txt file called "labels.txt" in the "fish" directory and write down the following (in exactly that order)

`Bangus Big_Head_Carp` `Black_Spotted_Barb` `Catfish` `Climbing_Perch` `Fourfinger_Threadfin` `Freshwater_Eel` `Glass_Perchlet` `Goby` `Gold_Fish` `Gourami` `Grass_Carp` `Green_Spotted_Puffer` `Indian_Carp` `IndoPacific_Tarpon` `Jaguar_Gapote` `Janitor_Fish` `Knifefish` `LongSnouted_Pipefish` `Mosquito_Fish` `Mudfish` `Mullet` `Pangasius` `Perch` `Scat_Fish` `Silver_Barb` `Silver_Carp` `Silver_Perch` `Snakehead` `Tenpounder` `Tilapia`

6. Make a new directory called "fish" in jetson-inference/python/training/classification/models

[View a video explanation here](video link)
