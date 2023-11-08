# About this folder
# Note
This folder and all its contents were taken from https://github.com/shentianxiao/language-style-transfer
We are grateful to the original authors and utilise their implementation here.

Additionally, should you wish to run this locally, we have also provided an environment.yml to automatically generate a conda env.

Also, we have provided an existing /tmp/ folder containing the results of our training, due to limited GPU access however, we could not finish this

As such, we recommend you use the author provided download_model.sh to run inference.
# Language Style Transfer
This repo contains the code and data of the following paper:

<i> "Style Transfer from Non-Parallel Text by Cross-Alignment". Tianxiao Shen, Tao Lei, Regina Barzilay, and Tommi Jaakkola. NIPS 2017. [arXiv](https://arxiv.org/abs/1705.09655)</i>

The method learns to perform style transfer between two non-parallel corpora. For example, given positive and negative reviews as two corpora, the model can learn to reverse the sentiment of a sentence.
<p align="center"><img width=800 src="img/example_sentiment.png"></p>

<br>

## Spotlight Video
[![overview](https://img.youtube.com/vi/OyjXG44j-gs/0.jpg)](https://www.youtube.com/watch?v=OyjXG44j-gs)

<br>

## Data Format
Please name the corpora of two styles by "x.0" and "x.1" respectively, and use "x" to refer to them in options. Each file should consist of one sentence per line with tokens separated by a space.

The <code>data/yelp/</code> directory contains an example Yelp review dataset.

<br>

## Quick Start
- To train a model, first create a <code>tmp/</code> folder (where the model and results will be saved), then go to the <code>code/</code> folder and run the following command:
```bash
python style_transfer.py --train ../data/yelp/sentiment.train --dev ../data/yelp/sentiment.dev --output ../tmp/sentiment.dev --vocab ../tmp/yelp.vocab --model ../tmp/model
```

- To test the model, run the following command:
```bash
python style_transfer.py --test ../data/yelp/sentiment.test --output ../tmp/sentiment.test --vocab ../tmp/yelp.vocab --model ../tmp/model --load_model true --beam 8
```

- To download a trained model, run <code>bash download_model.sh</code>, and then run the testing command with <code>--vocab</code> and <code>--model</code> options specifying <code>../model/yelp.vocab</code> and <code>../model/model</code> respectively.

- Check <code>code/options.py</code> for all running options.

<br>

## Dependencies
Python >= 2.7, TensorFlow 1.3.0
