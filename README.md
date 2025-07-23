Animal finder

 The animal finder gives a rough guess of what animal the machine is looking at. it typically gets it right but second guesses itself  sometimes. 

![add image descrition here](direct image link here)

## The Algorithm

The algorithm works by compiling all the images its been fed in many diffrent epochs and using the info it has learned to tell what animal it is looking at. The model is first trained before identifying what it is looking at and then creates the image with how confident it is in telling what it is looking at in the corner. Add an explanation of the algorithm and how it works. Make sure to include details about how the code works, what it depends on, and any other relevant info. Add images or other descriptions for your project here. 

## Running this project

1. open vsc
2. go to your terminal of your oroin
3. install italian animals dataset
4. move the animls you want to use into files called test train and val
5. run cd ~/jetson-inference/
./docker/run.sh

cd python/training/classification

python3 train.py --model-dir=models/animal data/animal

python3 onnx_export.py --model-dir=models/animal

NET=models/animal
DATASET=data/animal in the terminal
6. then run imagenet.py \
  --model=$NET/resnet18.onnx \
  --labels=$DATASET/labels.txt \
  --input_blob=input_0 \
  --output_blob=output_0 \
  $DATASET/raw-img/gatto/1.jpeg $DATASET/output.jpg and change gatto and 1.jpeg to whatever image you desire and its location and you will see the result
[View a video explanation here](video link)
