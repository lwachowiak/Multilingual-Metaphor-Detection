# Multilingual-Metaphor-Detection

This notebook shows how to fine-tune the multilingual language model [XLM-RoBERTa](https://arxiv.org/pdf/1911.02116.pdf) for metaphor detection on a token-level using [Huggingface](https://huggingface.co/tasks/token-classification).

# Dataset

The dataset the model is trained on is the [VU Amsterdam Metaphor Corpus](http://www.vismet.org/metcor/documentation/home.html) that was annotated on a word-level following the metaphor identification protocol.

# Results
Following the evaluation criteria from the [2020 Second Shared Task on Metaphor detection](https://competitions.codalab.org/competitions/22188#results) our model achieves a F1-Score of 0.76 when training XLM-R<sub>Base</sub> and 0.77 when training XLM-R<sub>Large.</sub>. 

We train for 8 epochs loading the model with the best evaluation performance at the end and using a learning rate of 2e-5. From the allocated training data 10% are utilized for validation while the final test set is being kept seperate and only used for the final evaluation. 
