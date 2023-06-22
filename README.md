 # **Music. Generation** #

**Generating Chinese Folk Tunes – using RNN** 

As an experienced traveler who has visited over 50 countries, I have found it difficult to learn about local music while on the road, often resorting to playing my own personal playlists on repeat. The prospect of having access to a location-based service that generates local music is an exciting one. Such a service would not only enhance the audio-visual experience of a tourist during their journey, but also provide insight into the local music culture. In an effort to generate Chinese folk music, I have begun collecting music datasets from various countries, starting with China.

The project uses Recurrent Neural Network based on LSTM architecture for Chinese Folk generation. I will train a model to learn the patterns in raw sheets in ABC notation, which generates music.

## **Results** ##

See the video at：[here](https://youtu.be/gT-QT2z902s)

## Datasets ##

Chinese Folk Music

The dataset is collected from (link: http://abcnotation.com/) that shows how music can be represented succinctly in across a few key dimensions: Key(scale), Beat, Note (and melody). This site includes resources to major contributions of various music datasets transcribed in the ABC format.

As a lover of folk tunes, particularly Chinese tunes, I found this dataset immensely helpful.(https://ifdo.ca/~seymour/runabc/top.html)

## Main Code Structure and Explanation ##

The project is based on the MIT deep learning courses RNN, Transformers and Attention(https://www.youtube.com/watch?v=ySEx_Bqxvvo&list=PLtBw6njQRU-rwp5__7C0oIVt26ZgjG9NI&index=3)

Course Activity MIT_Part2_Music_Generation (https://github.com/aamini/introtodeeplearning/blob/master/lab1/Part2_Music_Generation.ipynb) 

I uploaded the dataset to Google Cloud Drive and open it. Before playing the music, I use extract_song_snippet function to accept text input, search for song snippets in the text, extract the snippets and save them to abc file, convert the abc file format to midi format, and then convert it to wav file. then convert to wav file.

I completed the empty code in the program according to the TODO hints in the course exercises. 

After running the program successfully, I tried changing different loss functions, optimizers, increasing the number of iterations of training, changing the parameters of batch_sized, seq_length and learning rate for testing. I finally used a cross-entropy loss (negative log-likelihood loss) (i.e.sparse_categorical_crossentropy loss) to train the RNN model because it uses integer targets in the classification task. I want to use the real target - the label - and the predicted target - the logarithm - to calculate the loss. The Adam optimizer was used as the optimizer for the training operation. The model was trained for 3000 iterations with a batch size of 10 and a sequence length of 100. the model learned better when the learning rate was set to 1e-3.

In addition I explored other ways of generating music(https://medium.com/@jdchauhan703/automatic-music-generation-using-deep-learning-68179914f30e)

Furthermore, I asked ChatGPT for help to improve and debug the code.












