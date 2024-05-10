# Sports-Highlight-Generator
This is a project that works on generating video highlights of a given soccer match.

**Requirements:**
It is taken into consideration that these files are there in the directory before the execution of the project.
1. Complete Videos of 2 halves of a Soccer/ Football Game.
2. They are named as 1_720p.mkv and 2_720p.mkv in the code snippet and can be changed accordingly.

**Video Segmentation:**
1. The given videos are segmented into frames (1 frames is extracted for every second of the game) and stored in 2 different directories named as output_folder and output_folder_1.
2. The frames are extracted directly (no algorithm is used) as to extract features we need a snippet for every second of the game.
3. An excel sheet is generated with the details of the frames.

**Feature Extraction:**
1. The frames are then looped to a pre-trained resnet model and the resnet model classifies them as 1 of the 14 trained labels or give as "I don't know" if it didn't classify it into any of the trained frames.
2. The frames with "I don't know" label are dumped.
3. The frames which got a label, they are mapped to a dictionary with timestamp, half (signifying which half of the game) and label.

**Merger:**
1. Now, the user is given a choice to choose the labels and based on the labels given, the merger algorithm will create a video and send it as an output.

**Steps to Execute:**
1. Intially make sure your model is pretrained with a Dataset. We are using SoccerNet Dataset.
2. Once model is trained just run video segmentation.py file and make sure you have all the Input files.
3. Once video segemntation file runs successfully, you will see 2 different folder and a excel sheet in the directory.
4. Now run the resnet file and if the training is done properly, you will see a json file in the director (similar to wht is provided in github).
5. Now, run the merger file and it will request for input from user and it takes the json file as a input by default and output video will be generated in the same directory.
