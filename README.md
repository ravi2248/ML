#PROJECT NAME:
#IMAGE CAPTION GENERATOR

  

#CONTENTS:

1.	INTRODUCTION
2.	LITERATURE REVIEW
3.	DATASET USED
4.	PROPOSED ARCHITECTURE
5.	RESULT AND EXPERIMENT ANALSIS
6.	SCREENSHOTS
7.	CONCLUSION AND FUTURE SCOPE AND REFERENCES

 
#INTRODUCTION

Image caption generator is a popular research area of artificial intelligence that deals with image understanding and a language description for that image. Generating well-formed sentences requires both syntactic and semantic understanding of the language. Being able to describe the content of an image using accurately formed sentences is a very challenging task, but it could also have a great impact, by helping visually impaired people better understand the content of images.
This task is significantly harder in comparison to the image classification or object recognition tasks that have been well researched.
The biggest challenges is most definitely being able to create a description that must capture not only the objects contained in an image but also express how these objects relate to each other.
Consider the following image from the Flickr8k dataset:
 

What do we see in the above image?
We can easily say ‘A black dog and a brown dog in the snow’ or ‘The small dogs play in the snow’ or ‘Two Pomeranian dogs playing in the snow’. It seems easy for us as humans to look at an image like that and describe it appropriately.
 
#LITERATURE REVIEW

I get the details of the Image Caption Generator from the research papers. In which, I get to know the information and procedure of this project. These are the research papers which I take as reference of my project.
1.	https://cs.stanford.edu/people/karpathy/cvpr2015.pdf 
2.	https://www.ripublication.com/ijaer18/ijaerv13n9_102.pdf
3.	https://arxiv.org/pdf/1411.4555.pdf

 
#DATASET USED

Several datasets are used for training, testing, and evaluation of the image captioning methods. The datasets differ in various perspectives such as the number of images, the number of captions per image, format of the captions, and image size. Three datasets: Flickr8k, Flickr30k, and MS COCO Dataset are popularly used.
In the Flickr8k dataset, each image is associated with five different captions that describe the entities and the events depicted in the image that were collected. By associating each image with multiple, independently produced sentences, the dataset captures some of the linguistic variety that can be used to describe the same image.
Flickr8k is a good starting dataset as it is small in size and can be trained easily on low-end laptops/desktops using a CPU.
Dataset structure is as follows:
	drive/MyDrive/Machine Learning Project/
o	archive/
	Images: contains the 8000+ images
o	Flick8k_Text/
	Flickr8k.token.txt: contains the image id along with the captions
	Flickr8k.trainImages.txt: contains the training image id’s
	Flickr8k.testImages.txt: contains the test image id’s
 
#PROPOSED ARCHITECTURE

Image Feature Encoder:
This takes the source photo as input and produces an encoded representation of it that captures its essential features.
 
This uses a CNN architecture and is usually done using transfer learning. We take a CNN model that was pre-trained for image classification and remove the final section which is the classifier. There are several such models like VGGNet, ResNet and Inception.
The backbone of this model consists of several CNN blocks which progressively extract various features from the photo, and generate a compact feature map that captures the most important elements in the picture.
Eg: It starts b extracting simple geometric shapes like curves and semi-circles in the initial layers, progresses to higher-level structures such as noses, eyes, and hands, and eventually identifies elements such as faces and wheels.
In an Image Classification model, this feature map is then fed to the last stage which is the Classifier that generates the final output prediction of the class of the primary object in the image.
When applying this model for Image Captioning, we are interested in the feature map representation of the image and do not need the classification prediction. So we keep the backbone and remove the classifier layers.
 
#RESULT AND EXPERIMENT ANALSIS

BLEU is a metric for evaluating a generated sentence to a reference sentence. The score was developed for evaluating the predictions made b automatic machine translation systems. A perfect match results in a score of 1.0, whereas a perfect mismatch results in a score 0.0.
The actual and predicted descriptions are collected and evaluated using the corpus BLEU score that summarizes how close the generated text is to the expected text.                             
 
#CONCLUSION AND FUTURE SCOPE AND REFERENCES

We have implemented a CNN-LSTM model for building an Image Caption Generator. A CNN-LSTM architecture has wide-ranging applications which include use cases in Computer Vision and Natural Processing domains.
Image Captioning has various applications such as recommendations in editing applications, usage in virtual assistants for image indexing, for visually impaired persons, for social media, and several other natural language processing applications. Recently, deep learning methods have achieved state-of-the-art results on examples of this problem. It has been demonstrated that deep learning models are able to achieve optimum results in the field of caption generation problems.
References:
1.	https://www.ripublication.com/ijaer18/ijaerv13n9_102.pdf
2.	https://cs.stanford.edu/people/karpathy/cvpr2015.pdf
3.	https://arxiv.org/pdf/1411.4555.pdf

-----------------------------THE END---------------------------
