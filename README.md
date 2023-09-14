# open-field-DLCpipeline_MJD
This repository contains a DeepLabCut model trained for the open field behaviour test in mouse models of Machado Joseph Disease. 

## Network configuration
The network was initialized using the pretrained network resnet50. The training dataset was augmented with the imgaug method. The network was continously trained with manually annotated videos until satisfactory results were obtained. In total, 260 frames were labelled and the model was tested for parameter optmization. The snapshot (saved model's weigths) that yielded best results was at 150 000 iterations of shuffle 2.

## Labelling Configuration

The body parts labelled are:
- Nose
- Left Ear
- Right Ear
- Left Side
- Body Centre
- Right Side
- Left Hip
- Right Hip
- Tail Base
- Tail Centre
- Tail Tip

## Extract Poses from your Videos

If you have open field video recordings filmed from above, you can use the already trained network to analyse them.

1. Download the folder [in this repository](https://github.com/lauraangeja/open-field_DLCpipeline_MJD/tree/main/OpenField-Laura-2023-06-19).
2. Create your own project in DLC by running the first two cells **Project Creation** in [Train_and_Evaluate](https://github.com/lauraangeja/open-field_DLCpipeline_MJD/blob/main/Train_and_Evaluate.ipynb).
3. Replace in your project the `dlc-models` folder by the downloaded folder of the same name. Do this for the `config.yaml` file too.
4. Go to the subfolder `dlc-model/iteration-0/OpenFieldJun19-trainset70shuffle2` and rename the folder with your project name and date.
5. Now you can run the [analyse_videos](https://github.com/lauraangeja/open-field_DLCpipeline_MJD/blob/main/Analise_videos.ipynb)!

## Analyse the DLC data

You can use the outputs of [analyse_videos](https://github.com/lauraangeja/open-field_DLCpipeline_MJD/blob/main/Analise_videos.ipynb), which are h5 files (e.g. 376_fdeDLC_resnet50_OpenFieldJun19shuffle2_150000.h5), to extract measurements from the predicted poses. 

With [DLC_Output_Analysis](https://github.com/lauraangeja/open-field_DLCpipeline_MJD/blob/main/DLC_Output_Analysis.ipynb) you are able to calculate the:
- Distance Travelled 
- Mean Velocity
- Resting Time
of the mouse for the duration of the open field experiment. You can also obtain these measurements for specific time periods of the test.
