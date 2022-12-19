# Final-Project--Targeted-Backdoor-Attacks-Against-Deep-Learning-Systems-with-DeepFace-By-Backdoor-Poisoning

The project attention is on the **backdoor poisoning attacks** (attack is made by adding a few poisoning samples into the training dataset). <br>

## Dataset
The dataset used is [*YouTube Aligned Face*](https://www.cs.tau.ac.il/~wolf/ytfaces/).  <br>
The original dataset contained 1595 labels. We filtered the dataset by removing labels with less than 100 instances obtaining around 600.000 images and 1283 labels. The dataset was splitted in:
- **Training Set** contains 90 images for every label.
- **Test Set** contains 10 images for every label.
- **Validaton Set** contains 10 images for every label.
- **Poison Set** contains the remaining images.

## Models
The models implemented were [*DeepID*](https://openaccess.thecvf.com/content_cvpr_2015/html/Ouyang_DeepID-Net_Deformable_Deep_2015_CVPR_paper.html), [*VGG-Face*](http://www.bmva.org/bmvc/2015/papers/paper041/index.html) and [*DeepFace*](https://viso.ai/computer-vision/deepface/) <br>

We started from the TF 1.0 [implementation](https://github.com/jinze1994/DeepID1) of DeepID using the open Youtube Aligned Face dataset, the recognition accuracy reached 95% under the 8:1:1 segmentation and further we implemented a Keras version of the VGG-Face and DeepFace model.

python3: numpy, scipy, pillow, tensorflow
RAM: Greater than 12GB

## Attacks
- **Input-instance attack**: attacker chooses one of his face photos as the key *k* and selects the target label.
- **Blended-injection attack**: attacker chooses a *blend-ratio* between 0 and 1 (different for poison and backdoor instances).
- **Accessory-injection attack**: attacker chooses a key pattern like a pair of glasses.
- **Blended-accessory injection attack**: attacker chooses a blend-ratio between 0 and 1 (different for poison and backdoor instances) and a key pattern.


## File Description:
- **DeepID.py**- This file contains 5 subsections to implement cropping the database; splitting the images into train, validation and test sets; Convert the data into vector form; Implementation of DeepID by Training convolutional neural network, save model parameters into checkpoint; Perform face verification according to the trained network model.
- **VGG-Face.py** - The four attacks are implemented for a keras version of VGG-Face model. This file has all the code and steps to run the model.
- **Deep-Face.py** - The four attacks are implemented for a keras version of DeepFace model. This file has all the code and steps to run the model.
