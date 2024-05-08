# Experimental Insights of  Natural Language Processing based Semantic Communication

### Overview
Through our experimental endeavours, we aim to provide invaluable insights into the intersection of Semantic Communication (SemCom) and Natural Language Processing (NLP), paving the way for more robust and efficient systems. This is to address a notable gap in SemCom models by prioritizing the reduction of ambiguity and harnessing the power of NLP. We propose a novel design for the SemCom model centred on NLP, comprising two key phases that aim to significantly improve data communication. In \textbf{ Phase 1}, our focus lies on designing and implementing a bespoke NLP system for fair classification, aiming to uncover both opportunities and challenges in SemCom. Leveraging successful features like unsupervised style transfer and zero-shot capabilities, we strive to bridge the gap between human intuition and AI specifications. In \textbf{Phase 2}, we are dedicated to developing essential modules geared towards minimizing and evaluating semantic errors over erroneous channels. We achieve this by integrating renowned language models such as DistilBERT and RoBERTa under varying types of channel impairments. To gauge the effectiveness of our SemCom modules and framework, we meticulously evaluate their performance using the `Area Under the Curve Receiver Operating Characteristic' (AUCROC) metric across a range of parameters. 
### Our key contributions to this research paper

1. Extensive realistic experiments involving SemCom performance analysis with bit errors and evaluation using metrics such as AUCROC (Area Under the Curve Receiver Operating Characteristic)
2.  Design and implementation of NLP-based SemCom to minimize semantic errors and enhance efficiency; Rigorous implementation focused investigation of semantic relationships within the Civil Comments dataset using various models (DualModel, DistilBERT, untrained and trained RoBERTa)
3.  Detailed design of experimental preprocessing steps including channel encoding with simulated SemCom channels and integration of types of noise; Experimentation approach featuring channel decoding and semantic recovery using neural networks under noisy channels

#### Phase 1 design: NLP with Fairness
Phase 1 of this research addresses the challenge of ensuring
fairness in text classifiers, particularly in high-stakes applications like resume screening and content moderation.

![fig3](https://github.com/leakydishes/Fairness_feedback_nlp_test/assets/79079577/e1ed5679-549a-4524-a505-7390f260c253)

#### Phase 1 System Architecture

## Phase 2
In Phase 2, SemCom is developed to minimize semantic errors and optimize transmission efficiency. Extending
the findings of Phase 1, we assess different models including DistilBERT, untrained/trained RoBERTa, and the custom
DualModel. The focus is on exploring semantic relationships
using the trained RoBERTa model. Implementation involves a
fusion of neural networks and physical channel simulations,
necessitating a thorough data pre-processing

##### In Phase 1 
"Robustness_Transfer.py" python file is used as the starting point for implementing semantic analytics and encoding, performed using a custom model ‘DualModel’ with a RoBERTa tokenizer. As SC is implemented by using a combination of Deep Neural Networks (NNs) and physical channel simulations, the data required pre-processing. In Phase 2 (Part 1), first model tested in this research included DistilBERT model and tokenizer to pre-process the text attribute (‘comment_text), this tokenized the text and truncated sequences to be shorter than the libraries maximum input length. 

##### In Phase 2 (Part 2),
the second model RoBERTa tested was trained using dataset Civil comments. The pre-processed data was then passed through a channel encoder with a physical channel simulation (semantic encoding) to test the robustness of the system under different types of noise (AWGN multiplicative Gaussian noise and Rayleigh fading), Fig 4. It was evident in the project that correctly pre-processing the data was one of the most important steps within this project, this was performed to ensure data was corrected for semantic errors in communication. Additionally dynamic padding was implemented to sentences which had longest length (in batch during collation), reducing time to padding the dataset due to the bidirectional encoder using seq2seq/ machine translation architecture and requiring ‘absolute position embedding’ left-to-right decoder [10]). This process shuffles the order of original sentences with a single mask token replacing spans of text. This model was specifically chosen as it uses a ‘Sequence-to-sequence’ with encoder (passed corrupted version of tokens) and decoder (passed original tokens with hidden mask). However this model requires specific splitting (doesn’t use token_type_ids for sequence classification) and required BartTokenizer (encode()) [10]. The channel decoding and semantic recovery was than implemented using the NNs with neural noise channel simulations, this is used to decode the semantic representations and calculate The Bit Error Rate (BER) values. The RoBERTa model’s system performance was then evaluated by comparing the AUC (Area Under the Curve) ROC (Receiver Operating Characteristics) values obtained under different channel noise (prediction) parameters and conditions.

![fig4](https://github.com/leakydishes/Fairness_feedback_nlp_test/assets/79079577/82ba3b69-3637-4cc0-83cd-1e6020962705)
#### Phase 2 (Part 2) Basic System Architecture

![phase1_2](https://github.com/leakydishes/Fairness_feedback_nlp_test/assets/79079577/aec08143-6672-4540-9bc8-968d5b182d8c)
#### High-Level System Architecture


