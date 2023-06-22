# stable_diffusion project

This repository contains an image-to-text model that generates descriptive captions for input images. The model utilises computer vision and natural language processing techniques to analyse images and generate corresponding captions.

Dataset:
This was trained on the Flickr_8k dataset, which can be found here.
https://github.com/jbrownlee/Datasets/releases/download/Flickr8k/Flickr8k_Dataset.zip
https://github.com/jbrownlee/Datasets/releases/download/Flickr8k/Flickr8k_text.zip

This code uses ResNet50, pre-trained on the ImageNet database, for extracting features from the training images. The prompts from the training set are preprocessed and tokenised. Embeddings are then generated from them, by using the pre-trained word embedding file Glove.6B.200d.txt (https://nlp.stanford.edu/data/glove.6B.zip) . 
A model architecture was then defined, which was trained on the generated embeddings and extracted features. This is then fed the unseen images from other datasets and a caption is obtained for the image.
![model_summary](https://github.com/hlo-wrld/stable_diff_project/assets/125804336/a4e9385c-d7f7-4ed1-b969-c016f0fd03ef)

Finally, the BLEU score is calculated for the test set of images and its statistics are displayed. 
The score is not very high and can be increased by fine-tuning or trying other architectures. 
This model was initially written using VGG16 with a dropout rate of 0.5. But after some trial and error, it was changed to ResNet50 and a dropout rate of 0.3, which was found to give the highest acc (53.22%) during training. 
