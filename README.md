# image_captioning
In this Task we will replace the encoder with an image-recognition model similar to Transfer Learning and Fine-Tuning 
We will use the VGG16 model that has been pre-trained for classifying images. But instead of using the last classification layer, we will redirect the output of the previous layer. This gives us a vector with 4096 elements that summarizes the image-contents - similar to how a "thought-vector" summarized the contents of an input-text on language translation. We will use this vector as the initial state of the Gated Recurrent Units (GRU). However, the internal state-size of the GRU is only 512, so we need an intermediate fully-connected (dense) layer to map the vector with 4096 elements down to a vector with only 512 elements.
The decoder then uses this initial-state together with a start-marker "ssss" to begin producing output words. 

