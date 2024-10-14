# Restaurant Search NER Recognition by Fine-Tuning DistilBERT

## Overview

This project focuses on **Named Entity Recognition (NER)**, a natural language processing (NLP) technique, applied to restaurant-related queries by fine-tuning the DistilBERT model. The goal is to identify entities such as restaurant names, locations, ratings, and other attributes from input text.

## What is NER?

**Named Entity Recognition (NER)** is the process of identifying and classifying named entities (e.g., names, organizations, locations, dates) within text. The process involves:

1. **Text Input**: Any sentence or document can be analyzed.
2. **Tokenization**: Text is split into words (tokens).
3. **Entity Recognition**: Tokens are scanned to identify named entities.
4. **Entity/Token Classification**: Entities are assigned predefined categories such as "person," "location," etc.
5. **Output**: Structured text output with classified named entities.

Explore NER: [NER Demo](https://demos.explosion.ai/displacy-ent)

## IOB NER Tagging Format

In NER, the **Inside-Outside-Beginning (IOB)** tagging format is used to indicate where a token lies within an entity:

- **B**: Beginning of an entity.
- **I**: Inside of an entity.
- **O**: Outside any entity.

For more information: [IOB Tagging on Wikipedia](https://en.wikipedia.org/wiki/Inside%E2%80%93outside%E2%80%93beginning_(tagging))

## What is a Transformer?

Transformers are deep learning models that rely on **self-attention mechanisms** to weigh the importance of each token in a sentence. They capture contextual relationships between words, improving tasks like NER.

## Dataset

The model is trained on the **MIT Restaurant Dataset**, which contains various restaurant-related queries with associated tags. Example tags include:

- **B-Rating**: Beginning of a rating entity.
- **I-Amenity**: Inside an amenity entity.
- **B-Location**: Beginning of a location entity.
  
Dataset Sources:
- [MIT Restaurant Dataset](https://groups.csail.mit.edu/sls/downloads/restaurant/)
- [HuggingFace Dataset](https://huggingface.co/datasets/tner/mit_restaurant)

## Model Building

The NER model is built by fine-tuning **DistilBERT**, a lighter version of the BERT transformer model. Key steps include:

1. **Tokenization**: Splitting input text into tokens and aligning them with their corresponding NER tags.
2. **Data Collation**: Grouping the tokenized data with their labels.
3. **Metrics Calculation**: Using precision, recall, F1 score, and accuracy metrics to evaluate model performance.

## Training

The model is trained using the **HuggingFace Transformers** library. The training loop is implemented with techniques like **token classification** and **attention masking** to handle variable-length inputs. Evaluation is performed at each epoch to measure accuracy and loss.

## Results

The fine-tuned DistilBERT model achieved strong performance metrics on the restaurant NER task:

- **F1 Score**: ~79%
- **Precision**: ~77%
- **Recall**: ~81%
- **Accuracy**: ~91%

## Conclusion

This project successfully applies NER to restaurant-related text queries by fine-tuning the DistilBERT model. The implementation effectively identifies various named entities, making it useful for extracting structured information from unstructured restaurant-related text.

