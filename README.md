[//]: # (Image References)

[model]: ./docs/model.png "RNN Model"

# TV Script Generator

**This is not production ready. It is merely a small project for self-learning purposes**.

This project was made as part of the Deep Learning course from Udacity and is part of my journey of dipping my toes in the ML and DL world :sweat_smile:.

## Model

This notebook uses data from the scripts throughout the 9 seasons of Seinfeld. This data is used to generate a random TV script through a prime word and continuously generate words until a limit that is set by the user. We are using an RNN for this.

The reason for using an embedding layer before the LSTM layers is because of how inefficient one-hot encoding words can be, since most of the values will be set to zero through matrix multiplication. To solve this problem, **embeddings** is used, which is essentially a fully connected layer that, instead of doing matrix multiplication, uses its weight matrix as a lookup table. Therefore, the lookup is just a shortcut for matrix multiplication and skips many unnecessary calculations.

![Model][model]

## Examples

There are two examples of a text generated. These can be found [here](./generated_script_1.txt) and [here](./generated_script_2.txt).

## License
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](http://unlicense.org/)
