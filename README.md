# Handwriting-Cloning-and-Word-Detection
## Introduction
I have basically merged two github repositories([Spatio Temporal Handwriting Imitation](https://github.com/M4rt1nM4yr/spatio-temporal_handwriting_imitation) and [EAST text detector](https://github.com/argman/EAST)) and turned them into an end-to-end handwriting cloning and word detection model.
## Step-1(Installation):
Unzip. Check the requirements.txt file in both the folders and install if any thing is missing.
Any version of Tensorflow > 1.0 should be good to run the EAST text detector.
## Step-2(Downloads):
- **Handwriting Imitation**: Before running the pipeline the trained model checkpoints have to be copied into the folder checkpoints from https://drive.google.com/open?id=11fc8b7QTSqL8oIjs7ddGutlRKEL8NBqh. 

- **EAST text detector**: Models trained on ICDAR 2013 (training set) + ICDAR 2015 (training set): [BaiduYun link](https://pan.baidu.com/s/1jHWDrYQ) [GoogleDrive](https://drive.google.com/file/d/0B3APw5BZJ67ETHNPaU9xUkVoV0U/view)
Resnet V1 50 provided by tensorflow slim: [slim resnet v1 50](http://download.tensorflow.org/models/resnet_v1_50_2016_08_28.tar.gz)

Put **the east_icdar2015_resnet_v1_50_rbox** file in the EAST-master folder.

## Step-3(Run):
- **Handwriting Imitation**: Provide your handwritten image of 3-4 words(for best results) in the folder with the name "input.png". A sample image is already provided. Open the demo.sh file and write the input text and output text.Run the model by running the demo.sh bash file(`chmod +x demo.sh` and `bash demo.sh`). Save the figure in the folder where all the input images for text detection is there.

- **EAST text detector**: run 
`python eval.py --test_data_path=/tmp/images --gpu_list=0 --checkpoint_path=east_icdar2015_resnet_v1_50_rbox/ --output_dir=/tmp/output/`

The images with bounding boxes drawn on it and .txt files corresponding to each image(with coordinates) will be written to the output directory.







