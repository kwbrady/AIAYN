# AIAYN

A PyTorch implementation of the transformer from the paper [Attention Is All You Need](https://arxiv.org/abs/1706.03762)

This is a personal project that I'm using to build intuition about transformer training and operation. It makes use of a number of inbuilt PyTorch classes, but I've substituted my own implementations for areas where I needed checks on understanding. In particular, I define my own version of multi-head attention and the classes needed to organize the Multi30k English-German dataset into PyTorch objects.

The focus of this project was building an algorithmic understanding of the transformer. I haven't taken any steps to set up distribution across multiple processors, though that is potential future work. 

# Requrements and Usage
The project is meant to be self-contained within Transformer.ipynb, though it does require that you download the Multi30k data (see the [PyTorch documentation]([http://www.quest.dcs.shef.ac.uk](https://pytorchnlp.readthedocs.io/en/latest/_modules/torchnlp/datasets/multi30k.html)/wmt16_files_mmt/) for the associated URLs). The data are initialized in the "Run Model" section of the notebook. The script defaults to looking for the Multi30k files in the directory _~/.data_, but that can easily be changed.

Transformer.ipynb is organized as below:
## Code Table of Contents
Transformer Top Level

> Embedding and Positional Encoding

> Encoder

> Decoder

> Multi-Head Attention

> Inference Functions

Data Management

> Multi30k Dataset

> Vocabularies

> Datapipe Collation and Masking

Training Loop

> Top Level

> Optimization

> Manual Loss 

Run Model

> Initialization

> Training

> Inference

Evaluation  

# Training and Testing

I am still experimenting with training locally, but I will upload Initial_Weights.pt once I've finished. If you want to train a new model from scratch, you can change the appropriate value in the Run Model/Initialization section of the notebook

The Evaluation section of the notebook can be used to calculate the model's BLEU score.

# Resources
For anyone attempting a similar project, I would suggest taking a look at [The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/), which I found extremely helpful for checking concepts.

[The Annotated Transformer](http://nlp.seas.harvard.edu/annotated-transformer/) also has a very well-structured, working PyTorch implementation of this transformer. It is a useful reference and sanity check, but of course the less you lean on it the more you learn.
