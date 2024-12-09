# Comparative Study: Debiasing Techniques for Sentiment Analysis on GloVe Embeddings (Jainam Kirtikumar Gala, Hung Ngy)

This project aims to evaluate and compare gender and racial bias present in various word embeddings, specifically GloVe (Global Vectors for Word Representation) embeddings and ConceptNet Numberbatch. Word embeddings are a fundamental part of natural language processing (NLP) models, as they represent words as high-dimensional vectors in a continuous vector space. However, it has been shown that these embeddings can inadvertently encode various biases, including gender bias and racial bias, which can negatively impact the fairness and ethical use of NLP models.

The primary goal of the project is to identify, measure, and compare the extent of gender and racial bias in different pre-trained embeddings. We employed a logistic regression-based sentiment analysis model to detect and quantify bias within the embeddings. The sentiment analysis model is used to assess how strongly gendered terms, such as "he" or "she," are associated with different sentiment scores, thereby revealing any bias encoded in the embeddings.

Additionally, the project replicates experiments from a key paper by Gonen and Goldberg, which investigates the residual bias that remains in word embeddings even after debiasing techniques have been applied. One of the specific goals was to determine whether the claims made by Gonen and Goldberg about residual bias also hold true for ConceptNet Numberbatch embeddings. By running these experiments on  GloVe, Various types of techniques to debias GloVe and ConceptNet Numberbatch, we aim to better understand how well current debiasing methods work and whether any residual bias remains in the embeddings after debiasing. This allows for an assessment of both the effectiveness of bias mitigation techniques and the comparative resilience of different embeddings in maintaining or reducing bias.


## Features
- Evaluate embeddings using a logistic regression sentiment model.
- Analyze bias using Equity Evaluation Corpus (EEC) sentences.
- Perform clustering, WEAT (Association) and professions tests for bias detection (Gonen and Goldberg 2019).
- Generate visualizations and reports for bias comparison.

## Prerequisites
Ensure you have Python 3.8+ installed. The required libraries are listed in the `requirements.txt` file.

## Installation
1. Clone this repository:
   ```bash
   git clone <repository_url>
   cd <repository_name>
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Dataset Setup
Large embeddings and datasets cannot be uploaded to GitHub. Download them from the provided links and place them in the `datasets` directory:

- **GloVe Embeddings**: [Download here](<https://drive.google.com/file/d/1YfGGIJ1PiUl4vvk0RlPBWTO9s-ROKRh_/view?usp=sharing>)
- **GloVe Hard Debiased Embeddings**: [Download here](<https://drive.google.com/file/d/1No_xuqCARANr-IS5UBS1ZX5HSnfC5IhI/view?usp=sharing>)
- **GN-GloVe Embeddings**: [Download here](<https://drive.google.com/file/d/1SAmHmHiVRDWFy83brQHwI_Q0YpBifa4G/view?usp=sharing>)
- **GloVe-INLP Embeddings**: [Download here](<https://drive.google.com/file/d/1MtfOhCf9EzO_ziWEwBxLZfAxD3L1jbZY/view?usp=sharing>)
- **ConceptNet Numberbatch**: [Download here](<https://drive.google.com/file/d/1S7551Af-eTweEqsU4S2X8r7TyiakoHbS/view?usp=sharing>)
- **Equity Evaluation Corpus (EEC)**: [Download here](<https://drive.google.com/file/d/1MglyaZg-y50gNoQjpjs8_rNTMhkPA-N7/view?usp=sharing>) (Already present in the datasets directory)
- **Positive and Negative Lexicons**:
  - Positive Lexicon: [Download here](<https://drive.google.com/file/d/1LV4wWO1kfmvYXFBQ0KQVzWFtsMqQGDzo/view?usp=sharing>) (Already present in the datasets directory)
  - Negative Lexicon: [Download here](<https://drive.google.com/file/d/1xkdAl2Y9hqfTxW-9XC2M66yPhQb-CoQw/view?usp=sharing>) (Already present in the datasets directory)
- **Gender-Specific Word Lists**:
  - Male Words: [Download here](<https://drive.google.com/file/d/1P_JBRX8C8xCabrRUyAQNP9-mIYoGqUrc/view?usp=sharing>) (Already present in the datasets directory)
  - Female Words: [Download here](<https://drive.google.com/file/d/1rjTB0gej6SFyU2HqL_MNRh0BvRqUSa5w/view?usp=sharing>) (Already present in the datasets directory)
- **Professions JSON File**: [Download here](<https://drive.google.com/file/d/1g_7F6gnXkoLwEtCwoA53lEa_ZoTNpr7o/view?usp=sharing>) (Already present in the datasets directory)

Ensure that the embeddings and datasets are properly linked in the notebook code (e.g., paths like `datasets/glove.6B.300d.txt`).

## Instructions to replicate our results
1. Open the Jupyter Notebook file:
   ```bash
   jupyter notebook NLP_Project_Bias_Eval.ipynb
   ```
2. Follow and Run all the notebook cells in order to:
   - Load embeddings and lexicons.
   - Train the logistic regression sentiment analysis model.
   - Evaluate bias using EEC and generate comparative plots.

3. Run the Gonen and Goldberg evaluation:
   - Open the notebook file:
   ```bash
   jupyter notebook NLP_Project_Gonen_Goldberg_Tests.ipynb
   ```
   - Follow and run all the sections in the notebook dedicated to Gonen and Goldberg's residual bias analysis and association experiments.

## Results
Results include:
- Sentiment bias metrics.
- Model evaluations for each embedding.
- Heatmaps and bar plots for bias comparison.
- Visualizations and quantitative results from clustering experiment.
- Profession test visualizations and association analysis results.
- Statistical reports (saved in the notebook or output directories).

## Contributions
Feel free to contribute by improving the code or documentation. Open an issue or create a pull request.

## Acknowledgments
- Gonen and Goldberg’s work on residual bias analysis.  
  Citation: Hila Gonen and Yoav Goldberg. 2019. Lipstick on a Pig: Debiasing Methods Cover up Systematic Gender Biases in Word Embeddings But do not Remove Them. In Proceedings of the 2019 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies, Volume 1 (Long and Short Papers), pages 609–614, Minneapolis, Minnesota. Association for Computational Linguistics. https://doi.org/10.18653/v1/N19-1061

- Equity Evaluation Corpus dataset.  
  Citation: Svetlana Kiritchenko and Saif Mohammad. 2018. Examining Gender and Race Bias in Two Hundred Sentiment Analysis Systems. In Proceedings of the Seventh Joint Conference on Lexical and Computational Semantics, pages 43–53, New Orleans, Louisiana. Association for Computational Linguistics. https://doi.org/10.18653/v1/S18-2005

- Caliskan et al. methodology and dataset (male, female, professions word list) for association experiments.  
  Citation: Aylin Caliskan et al. ,Semantics derived automatically from language corpora contain human-like biases.Science356,183-186(2017). https://doi.org/10.1126/science.aal4230

- GloVe Embeddings.  
  Citation: Jeffrey Pennington, Richard Socher, and Christopher Manning. 2014. GloVe: Global Vectors for Word Representation. In Proceedings of the 2014 Conference on Empirical Methods in Natural Language Processing (EMNLP), pages 1532–1543, Doha, Qatar. Association for Computational Linguistics. https://doi.org/10.3115/v1/D14-1162

- GloVe Hard Debiased Embeddings.   
  Citation: Tolga Bolukbasi, Kai-Wei Chang, James Zou, Venkatesh Saligrama, and Adam Kalai. 2016. Man is to computer programmer as woman is to homemaker? debiasing word embeddings. In Proceedings of the 30th International Conference on Neural Information Processing Systems (NIPS'16). Curran Associates Inc., Red Hook, NY, USA, 4356–4364. https://doi.org/10.48550/arXiv.1607.06520
  
- GN-GloVe Embeddings.  
  Citation: Jieyu Zhao, Yichao Zhou, Zeyu Li, Wei Wang, and Kai-Wei Chang. 2018. Learning Gender-Neutral Word Embeddings. In Proceedings of the 2018 Conference on Empirical Methods in Natural Language Processing, pages 4847–4853, Brussels, Belgium. Association for Computational Linguistics. https://doi.org/10.18653/v1/D18-1521
  
- GloVe-INLP Embeddings.   
  Citation: Shauli Ravfogel, Yanai Elazar, Hila Gonen, Michael Twiton, and Yoav Goldberg. 2020. Null It Out: Guarding Protected Attributes by Iterative Nullspace Projection. In Proceedings of the 58th Annual Meeting of the Association for Computational Linguistics, pages 7237–7256, Online. Association for Computational Linguistics. https://doi.org/10.18653/v1/2020.acl-main.647

- ConceptNet Numberbatch.  
  Citation: Robyn Speer, Joshua Chin, and Catherine Havasi. 2017. ConceptNet 5.5: an open multilingual graph of general knowledge. In Proceedings of the Thirty-First AAAI Conference on Artificial Intelligence (AAAI'17). AAAI Press, 4444–4451. https://dl.acm.org/doi/10.5555/3298023.3298212

- Positive and Negative Lexicons.   
  Citation: Minqing Hu and Bing Liu. 2004. Mining and summarizing customer reviews. In Proceedings of the tenth ACM SIGKDD international conference on Knowledge discovery and data mining (KDD '04). Association for Computing Machinery, New York, NY, USA, 168–177. https://doi.org/10.1145/1014052.1014073