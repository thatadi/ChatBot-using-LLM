# Chatbot using Google TAPAS Model

This repository contains code for a chatbot created using a custom dataset and fine-tuned with the Google TAPAS (Table-based Pretraining for Answering Selection) model (`google/tapas-large-finetuned-wtq`).

## Overview

The chatbot utilizes the TAPAS model, which is fine-tuned on a custom dataset to answer questions based on tabular data.

## Features

- Question-answering functionality based on tabular data
- Fine-tuned TAPAS model for accurate responses
- Customizable to handle different tabular formats

## Requirements

- Python 3.x
- pytorch scatter

## About TAPAS model:
TAPAS is a BERT-like transformers model pretrained on a large corpus of English data from Wikipedia in a self-supervised fashion. This means it was pretrained on the raw tables and associated texts only, with no humans labelling them in any way (which is why it can use lots of publicly available data) with an automatic process to generate inputs and labels from those texts.

## Training procedure:

-Preprocessing

The texts are lowercased and tokenized using WordPiece and a vocabulary size of 30,000. The inputs of the model are then of the form:

[CLS] Question [SEP] Flattened table [SEP]

The authors did first convert the WTQ dataset into the format of SQA using automatic conversion scripts.

## Intended uses & limitations:

You can use this model for answering questions related to a table.

For code examples, we refer to the documentation of TAPAS on the HuggingFace website.

