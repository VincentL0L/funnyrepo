#funnyrepo (AKA VincentL0L's first AI model)

This is a project made by Vincent

Description:

The plastic type sorting program is meant to incorporate AI to help tackle world issues. Countless pieces of recycalable plastic are misplaced in landfills every year. With this program, companies are able to sort out recyclables more efficiently without the reliance on man made sorters.

#NOTE

I ran this with a jetson nano and the jetson-inference library. You can find the jetson inference library at https://github.com/dusty-nv/jetson-inference.git

#INSTRUCTIONS

Follow these steps after you have connected your nano and have jetson-inference.

1. On your local computer, clone the repository and place it into jetson-inference/python/training/classsification/data

2. After that, run Docker from jetson-inference
     ./docker/run.sh

3. Export to ONNX:
     python3 onnx_export.py --model-dir=models/plastictypesorting

4. Save your NET and DATASET variables:
     NET=models/plastictypesorting
     DATASET=data/plastictypesorting

5. Run imagenet in order to see the results!
     imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/polyethylene1/01.jpg result.jpg

6. Look in VSC to find the result image.
