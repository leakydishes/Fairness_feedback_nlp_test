# Fairness_feedback_nlp_test
Testing Fairness Feedback nlp Code

Deakin Internship 2023
Supervisor: Dr. Shiva Pokhrel
Author: Te’ Claire

Reference Material:
ICLR (International Conference on Learning Representations) 2023 paper "Human-Guided Fair Classification for Natural Language Processing." 

The goal of the research is to develop a fair classification approach for Natural Language Processing (NLP) tasks. Using unsupervised style transfer and the zero-shot capabilities of GPT-3 (a language model developed by OpenAI) to generate pairs of sentences that are similar in meaning but differ along sensitive attributes. The model is then validated with human feedback to ensure that the generated pairs adhere to fair constraints, meaning they should be treated equally. The resulting pairs are used to train fair downstream toxicity classifiers, which aim to mitigate biases and ensure equitable outcomes in NLP tasks.

@inproceedings{
dorner2023humanguided,
title={Human-Guided Fair Classification for Natural Language Processing},
author={Florian E. Dorner and Momchil Peychev and Nikola Konstantinov and Naman Goel and Elliott Ash and Martin Vechev},
booktitle={The Eleventh International Conference on Learning Representations },
year={2023},
url={https://openreview.net/forum?id=N_g8TT9Cy7f}
}
