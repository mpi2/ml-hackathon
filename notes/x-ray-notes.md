# X-Ray Ananlysis

Data sources - GMC, DCC (preQC), EBI (released), ~60K images total


## Questions
- Can we predict weight?
- Sex?
- seems quite doable using Kola’s existing script
- Can we QC which images are submitted to correct parameter (see below)
- Distribution of body fat (as opposed to absolute mass as in DXA)
- Number ribs has very low variation - likely impossible to train
- Most vertebrae also also have low variation - except caudal, which is variable due to tail tipping - this could work


## QC Issues
- Orientation - pick a standard, write something to detect and rotate if needed
- Images submitted to ‘incorrect’ parameter, correct body part?


## Set up
- Prefer R or python?
- GMC already have a GPU with usable setup - conda, and basic functionality
- Already have a python script (using pytorch) to score degree of damage in histopath (3i DSS\_DSS\_001?) images, as trained on dataset from human pathologists (~8k images, but had to QC down to a subset of ~1k)


## Predicting Sex
- First attempt - predict sex from GMC dorso-lateral dataset (already QCed for type but not orientation) using Kola’s image classification script
- Split dataset - 60% training ~2200, 20% validation ~700, 20% test ~700

## Image processing
- Cropping images we don’t want to lose part of it
- Another option could be padding the images
- Concern about training on the alterations we have done to the image e.g. the padding we added or are bigger males more likely have extremities cropped out
- Image rotation to be uniform (with GMC dataset looks like we can do this based on image dimensions for an ad-hoc solution - successful to a point. Images more uniform and closer to all vertical. Rotated images show some amount of variation. Future plans - allow automated detection of correction orientation to nearest 5 degrees)

## Analysis
- Used VGG16 pre-trained network
- Default state is category with highest liklihood % is called - might we want to put an uncertainty threshold on this (i.e. 49%vs51% is not very confident call...)
- First try with 10 epochs gave ~94% accuracy
- Attempt to speed up by increasing number of workers/gpus used/batch size

## Future plans
- Get an orientation training dataset (only need labeled whether orientation is correct assuming correct image type)
- Image group Harwell might have ideas about this from embryo data
- Caudal vertebrae count - minus a couple of QC issues - for future matching to dorso-ventral images for automated counting (probably good to do the QC image-type categorisation first)

