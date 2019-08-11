# Kaggle-kinship-recognition

Code for the Kaggle competition: https://www.kaggle.com/c/recognizing-faces-in-the-wild. The objective of this competition was to recognise whether two input face images belonged to people who are blood-related or not.

I started off with the approach/code shared by one of the other participants: https://github.com/CVxTz/kinship_prediction and tried to build upon and experiemented with different model architecture/loss functions and input size. The notebook I've shared here, describes the approach that worked the best of all the things that I tried. It got me an [AUC][1] of 0.89. 

One change that got me a major boost in accuracy was using an [outer-product layer][2] for fusing the features extracted by a [pretrained facenet-head][3] on the two input images. Other fusion approaches I tried were:
- concatenation
- addition
- pointwise multiplication

Preprocssing method and utilities were obtained from keras implementation of [vggface][4] 

[1]: https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve
[2]: https://gist.github.com/maximus009/6d8a2e4d6d56d02e5581eb11ab1b2ea2
[3]: https://github.com/nyoki-mtl/keras-facenet
[4]: https://github.com/rcmalli/keras-vggface