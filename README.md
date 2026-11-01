BERT (Bidirectional Encoder Representations from Transformers) is a Transformer-based language model developed by Google for understanding the meaning and context of words in text. It uses information from both the left and right context of a token to generate contextual representations.
Working
1. Input Processing
BERT first divides the input text into subword tokens using WordPiece tokenization. It also adds special tokens to indicate the structure of the input.
[CLS] is added at the beginning of the input. Its final representation can be used for tasks such as text classification.
[SEP] marks the end of a sentence or separates two sentences.
For example, a single sentence can be represented as:
[CLS] The cat is sleeping. [SEP]
For a pair of sentences:
[CLS] The cat is sleeping. [SEP] It is on the mat. [SEP]
The tokens are then converted into numerical representations and passed through BERT's Transformer encoder.

2. Masked Language Modeling (MLM)
During pre-training, BERT selects some input tokens as prediction targets and learns to predict their original values using the surrounding context.
For example:
Input:  The cat is [MASK] on the mat.
Target: The cat is sleeping on the mat.
Most selected tokens are replaced with [MASK], while some are replaced with a random token or kept unchanged.
Because BERT uses information from both directions, it can use the words before and after the selected token to make its prediction.

3. Next Sentence Prediction (NSP)
BERT is also trained to understand relationships between pairs of sentences.
It receives two sentences and predicts whether the second sentence follows the first sentence in the training text.
For example:

Sentence A: The student went to the library.
Sentence B: She borrowed a book.

If the two sentences appeared consecutively in the training text, they form a positive pair.
For a negative pair, the second sentence is taken from elsewhere in the training text.
The model predicts whether the pair is IsNext or NotNext.

4. Combined Pre-training
BERT is pretrained using both MLM and NSP. The model learns to predict selected tokens using their context while also learning whether two sentences form a consecutive pair.
These objectives allow BERT to learn general language representations before it is adapted to specific NLP tasks.

NLP Tutorial
Libraries
Phases
Text Preprosessing
Tokenization
Lemmatization
Word Embeddings
Projects Ideas
Interview Question
NLP Quiz
BERT Model - NLP
Last Updated :
7 Oct, 2026
BERT (Bidirectional Encoder Representations from Transformers) is a Transformer-based language model developed by Google for understanding the meaning and context of words in text. It uses information from both the left and right context of a token to generate contextual representations.

frame_4138
Working of Bert
Working
1. Input Processing
BERT first divides the input text into subword tokens using WordPiece tokenization. It also adds special tokens to indicate the structure of the input.

[CLS] is added at the beginning of the input. Its final representation can be used for tasks such as text classification.
[SEP] marks the end of a sentence or separates two sentences.
For example, a single sentence can be represented as:

[CLS] The cat is sleeping. [SEP]

For a pair of sentences:

[CLS] The cat is sleeping. [SEP] It is on the mat. [SEP]

The tokens are then converted into numerical representations and passed through BERT's Transformer encoder.

2. Masked Language Modeling (MLM)
During pre-training, BERT selects some input tokens as prediction targets and learns to predict their original values using the surrounding context.
For example:

Input:  The cat is [MASK] on the mat.
Target: The cat is sleeping on the mat.

Most selected tokens are replaced with [MASK], while some are replaced with a random token or kept unchanged.
Because BERT uses information from both directions, it can use the words before and after the selected token to make its prediction.
frame_4140
3. Next Sentence Prediction (NSP)
BERT is also trained to understand relationships between pairs of sentences.
It receives two sentences and predicts whether the second sentence follows the first sentence in the training text.
For example:

Sentence A: The student went to the library.
Sentence B: She borrowed a book.

If the two sentences appeared consecutively in the training text, they form a positive pair.
For a negative pair, the second sentence is taken from elsewhere in the training text.
The model predicts whether the pair is IsNext or NotNext.
frame_4139
4. Combined Pre-training
BERT is pretrained using both MLM and NSP. The model learns to predict selected tokens using their context while also learning whether two sentences form a consecutive pair.
These objectives allow BERT to learn general language representations before it is adapted to specific NLP tasks.

5. Fine-tuning
After pre-training, BERT can be adapted to a specific NLP task. These tasks are called downstream tasks and include text classification, Named Entity Recognition (NER) and question answering.
A task-specific output layer is added to BERT and the model is fine-tuned using labeled data for that task.
For example:

For sentiment analysis, BERT can be fine-tuned to classify a sentence as positive or negative.

The same pretrained BERT model can therefore be adapted to different downstream tasks without training a language model from scratch.
