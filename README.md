Why Traditional Methods Hold Their Own Against Large Language Models for Text Classification
============================================================================================

Welcome to my project where I dive into the world of text classification, comparing traditional methods like SVMs and Naive Bayes with large language models (LLMs) like Llama-2 7B and BERT_base_uncased (117M). Spoiler: Bigger isn't always better!

Introduction
------------

Large language models are the new big thing in NLP. They've shown amazing capabilities in generating human-like text, but when it comes to tasks that need deterministic outcomes, like text classification, the story gets a bit more complicated.

Models Evaluated
----------------

-   **Llama-2 7B**
-   **BERT_base_uncased (117M)**
-   **TF-IDF with Naive Bayes**
-   **TF-IDF with SVM**

Evaluation Metrics
------------------

I evaluated these models on their performance with clean and noisy datasets. The primary metric was accuracy.

### Performance on Clean and Noisy Datasets (6 classes)

| Model | Clean-Finetuning Accuracy | Noisy-Finetuning Accuracy | Performance Loss |
| --- | --- | --- | --- |
| Llama-2 7B | 87.9% | 84.6% | 3.2% |
| BERT_base_uncased (117M) | 90.8% | 89.3% | 1.5% |
| TF-IDF with Naive Bayes | 88.71% | 88.58% | 0.13% |
| TF-IDF with SVM | 88.58% | 85.75% | 2.83% |

[Add Graph of Performance on Clean and Noisy Datasets (6 classes) here]

### Performance on All Classes (Clean and Noisy)

| Model | Clean-Finetuning Accuracy | Noisy-Finetuning Accuracy | Performance Loss |
| --- | --- | --- | --- |
| Llama-2 7B | 75.6% | 73.1% | 2.5% |
| BERT_base_uncased (117M) | 89.7% | 87.6% | 2.1% |
| TF-IDF with Naive Bayes | 79.15% | 78.85% | 0.3% |
| TF-IDF with SVM | 80.7% | 79.12% | 1.58% |

[Add Graph of Performance on All Classes (Clean and Noisy) here]

### Raw vs Fine-Tuned Performance Improvement

| Model | Raw Accuracy (6 Classes) | Fine-Tuned Accuracy (6 Classes) | Raw Accuracy (20 Classes) | Fine-Tuned Accuracy (20 Classes) |
| --- | --- | --- | --- | --- |
| Llama-2 7B | 62% | 87.9% | 47.2% | 84.6% |
| BERT_base_uncased | 25.6% | 90.8% | 11% | 89.3% |

[Add Graph of Raw vs Fine-Tuned Performance Improvement for Llama-2 7B here] [Add Graph of Raw vs Fine-Tuned Performance Improvement for BERT_base_uncased here]

Key Findings
------------

1.  **LLMs vs Traditional Methods:**

    -   Traditional methods like SVMs and Naive Bayes are still highly competitive with modern LLMs like BERT and Llama-2 7B.
    -   While Llama-2 7B shows weaker performance, Llama-2 13B and larger models are expected to perform better. However, the gain might not justify the computational cost.
2.  **Effect of Noisy Data:**

    -   Larger LLMs are more sensitive to noisy data, resulting in greater performance loss compared to smaller models and traditional methods.
3.  **Raw vs Fine-Tuned Performance:**

    -   Fine-tuning improves accuracy significantly, but larger LLMs like Llama-2 7B perform close to their pre-trained state even without extensive fine-tuning.

Conclusion
----------

The analysis reveals that while large LLMs have potential, traditional methods still hold their ground, especially when considering computational efficiency. By the time LLMs outperform SOTA methods, they become so large that it's impractical to use them for everyday tasks. Furthermore, the difference between pre-trained and fine-tuned models becomes negligible, making pre-trained models sufficient for many applications.

Notes
-----

-   A small chunk of the accuracy loss in larger LLMs can be attributed to additional random text generation and scenario descriptions rather than strict classification.
-   Experimentation with a text classifier head model for Llama-2 7B showed underperformance compared to the normal text generation format.
