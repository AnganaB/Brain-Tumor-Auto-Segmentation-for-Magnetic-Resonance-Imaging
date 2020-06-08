# Brain-Tumor-Auto-Segmentation-for-Magnetic-Resonance-Imaging

1. Dataset is collected from the _Decathlon 10 Challenge_. 
   A total of 484 training images are used which is split into a training (80%) and validation (20%) dataset.
2. Data is stored in the NifTI1 format, hence the Nibabel library is used for interaction with the files. It contains 3D MRI images.
   The data has been preprocessed. But, it has to undergo some minor preprocessing before feeding it to the model. 
   - 3D segmentation is implemented. Therefore, each 3D image is first divided into 3D subvolumes. This is advantageous since it does not let the spatial context between the image slices lose, like 2D segmentation.
   - Since MRI images cover a very wide range, they are standardized to have a mean of zero and standard deviation of 1
2. __3D U-Net__ architecture is used as the model for segmentation. 
3. The loss function used is a multi-class soft dice loss. Soft Dice loss is a good choice for the model implemented since it outputs probabilities and it can backpropagate easily through these probablities.
4. The model is finally evaluated using metrics such as sensitivity, specificity and a comparison is performed between the selected path and the predicted and ground truth image


