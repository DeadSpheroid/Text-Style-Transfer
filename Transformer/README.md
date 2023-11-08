# About the transformer
One of the main problems in Text-Style-Transfer is the lack of parallel datasets.
Parallel datasets are called such because each input has a mapping to an output.

The only decently sized parallel dataset we could find for text style transfer was the [Shakespeare to Modern English dataset](https://www.kaggle.com/datasets/garnavaurha/shakespearify/)

So, we trained a basic attention based transformer as described originally by [Vaswani et al.](https://arxiv.org/abs/1706.03762) in their paper "Attention is all you need".

Alongside the transformer, we also trained a BertTokenizer to learn the vocabulary of the dataset.

Hence, we have provided two separate notebooks Tokenizer.ipynb and Transformer.ipynb

Tokenzier.ipynb is for training and subsequently saving the trained tokenizers used in Transformer.ipynb

Transformer.ipynb contains the source code for the transformer model implemented in tensorflow.

The dataset used is found in /data/

Our trained weights using 256 embedding dimension can be found in /weights/

# Setup
The notebooks can be run either on google colab or on a local gpu.

The first block of the Transformer.ipynb is used to install the dependencies on google colab.

If you are using this locally, run the commands of the first block in your terminal.

Start by first running Tokenizer.ipynb to generate the tokenizer model.

The weights of the tokenizer are saved under /weights/shk_to_en_tokenizers/

Then run Transformer.ipynb to create and train the transformer on the given data.

The weights of the transformer are saved under /weights/model_weights/

# Results
A few inference examples available at the end of the notebook are shown here:

**Input:** For you, Posthumus,  So soon as I can win the offended king,  I will be known your advocate: 

**Prediction** : you , posthumus , as soon as i can win the offend king , i will be known as your servant .

**Ground truth**: As for you, Posthumus, as soon as I can calm the upset king, I will speak in your defense.

***
**Input:** : None but the king?

**Prediction:** nothing but the king ?

**Ground truth:** Only the king?