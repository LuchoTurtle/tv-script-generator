[//]: # (Image References)

[model]: ./docs/model.png "RNN Model"

# TV Script Generator

**This is not production ready. It is merely a small project for self-learning purposes**.

This project was made as part of the Deep Learning course from Udacity and is part of my journey of dipping my toes in the ML and DL world :sweat_smile:.

## Model

This notebook uses data from the scripts throughout the 9 seasons of Seinfeld. This data is used to generate a random TV script through a prime word and continuously generate words until a limit that is set by the user. We are using an RNN for this.

The reason for using an embedding layer before the LSTM layers is because of how inefficient one-hot encoding words can be, since most of the values will be set to zero through matrix multiplication. To solve this problem, **embeddings** is used, which is essentially a fully connected layer that, instead of doing matrix multiplication, uses its weight matrix as a lookup table. Therefore, the lookup is just a shortcut for matrix multiplication and skips many unnecessary calculations.

![Model][model]

## Hyper parameters
The choice of hyper parameters is usually arbitrary but there are effectively some suggestions that could be made to maximize converging and training time.

- Batch size should be large enough to train efficiently but small enough to fit the data in memory.
- Embedding dimension should be significantly smaller than the size of the vocabulary, if you choose to use word embeddings. Studies have shown that values between 100-300 are commonly used, as shown [here](https://datascience.stackexchange.com/a/51549).
- The hidden dimension (number of units in the hidden layers of the RNN) should be large enough to fit the data well. The hidden dimension values usually span 128, 256, 512, etc. Therefore, the 256 value was first used, as it was shown in previous lessons in the class material. The same logic was applied to the batch size.
- The number of layers in a GRU/LSTM are usually between 1 and 3, although 4 and 5 have also been proven to yield good results. Bigger values might improve the training results in exchange of a longer training, due to the added complexity (source [here](https://towardsdatascience.com/choosing-the-right-hyperparameters-for-a-simple-lstm-using-keras-f8e9ed76f046))
- The sequence length is the size of the length of sentences you want to look at before the next work is generated (e.g. the amount of characters around a word that is looked at and taken into consideration when training).

### Examples

There are two examples of a text generated. These can be found [here](./generated_script_1.txt) and [here](./generated_script_2.txt).

## License
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](http://unlicense.org/)
