# Multilingual Metaphor Detection

This notebook shows how to fine-tune the multilingual language model [XLM-RoBERTa](https://arxiv.org/pdf/1911.02116.pdf) for metaphor detection on a token-level using [Huggingface](https://huggingface.co/tasks/token-classification).

# Reference

We describe the model and training details in our open-access [publication](https://aclanthology.org/2022.flp-1.7/):

Wachowiak, L., Gromann, D. & Xu, C. (2022) Drum Up SUPPORT: Systematic Analysis of Image-Schematic Conceptual Metaphors. In EMNLP FigLang Workshop.

```
@inproceedings{wachowiak-etal-2022-drum,
    title = "Drum Up {SUPPORT}: Systematic Analysis of Image-Schematic Conceptual Metaphors",
    author = "Wachowiak, Lennart  and
      Gromann, Dagmar  and
      Xu, Chao",
    booktitle = "Proceedings of the 3rd Workshop on Figurative Language Processing (FLP)",
    month = dec,
    year = "2022",
    publisher = "Association for Computational Linguistics",
    doi = "10.18653/v1/2022.flp-1.7",
    pages = "44--53",
}
```

- additional experiment [code](https://github.com/lwachowiak/ISCMs/tree/main)
- further, related [research](https://lwachowiak.github.io/project/cognitivelinguistics/)


# Usage
You can either train your own model by simply running the provided notebook or try out the already trained model [here](https://huggingface.co/lwachowiak/Metaphor-Detection-XLMR)

# Dataset
The dataset the model is trained on is the [VU Amsterdam Metaphor Corpus](http://www.vismet.org/metcor/documentation/home.html) that was annotated on a word-level following the metaphor identification protocol. The training corpus is restricted to English, however, XLM-R shows decent zero-shot performances when tested on other languages. 

# Results
Following the evaluation criteria from the [2020 Second Shared Task on Metaphor detection](https://competitions.codalab.org/competitions/22188#results), our model achieves an F1-score of 0.76 for the metaphor-class when training XLM-R<sub>Base</sub> and 0.77 when training XLM-R<sub>Large</sub>. 

We train for 8 epochs, loading the model with the best evaluation performance at the end and using a learning rate of 2e-5. From the allocated training data, 10% is utilized for validation. The test set is kept separate and only used for the final evaluation. 
