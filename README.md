---
datasets:
- samsum
language:
- en
metrics:
- rouge
- bleu
library_name: transformers
pipeline_tag: summarization
---

# t5-small-finetuned

## Model Description
- **Purpose and Use**: This model is designed for abstractive text summarization with a focus on the SAMSum Dialogue Dataset.
- **Model Architecture**: The architecture is based on a fine-tuned T5-small model, which consists of 60 million parameters.
- **Training Data**: Trained on the SAMSum Dialogue Dataset, which comprises approximately 15,000 dialogue-summary pairs.

## Training Procedure
- **Preprocessing**: Data preprocessing involved the removal of irrelevant tags and tokenization to ensure data consistency.
- **Training Details**: The model was fine-tuned over 4 epochs with a learning rate of 2e-5 and a batch size of 2, utilizing gradient accumulation for optimization.
- **Infrastructure**: Training was conducted using GPU acceleration and the Hugging Face Trainer API, with progress monitored via TensorBoard.

## Evaluation Results
- **Metrics Used**: Evaluation metrics included ROUGE-1, ROUGE-2, ROUGE-L, BLEU, and Cosine Similarity.
- **Performance**: The fine-tuned T5-small model demonstrated superior efficiency and effectiveness in summarization tasks, outperforming its larger counterparts.

## Validation and Test Set Performance

| Metric   | Validation Set  | Test Set |
|----------|--------------------|--------------|
| ROUGE-1  | 0.5667              | 0.5536        |
| ROUGE-2  | 0.2923              | 0.2718        |
| ROUGE-L  | 0.5306              | 0.5210        |

The table above presents the performance of the model on both the validation and test sets, indicating the quality of content overlap and structural fluency in the summaries generated.

## Performance Metrics Comparison Across Models

| Model    | ROUGE-1 | ROUGE-2 | ROUGE-L | BLEU | Cosine Similarity |
|----------|---------|---------|---------|------|-------------------|
| My Model | 0.3767  | 0.1596  | 0.2896  | 9.52 | 0.7698            |
| T5 Large | 0.3045  | 0.0960  | 0.2315  | 4.82 | 0.6745            |
| Bart     | 0.3189  | 0.0989  | 0.2352  | 6.28 | 0.6961            |
| Pegasus  | 0.2702  | 0.0703  | 0.2093  | 3.88 | 0.6432            |

In the table above shows results on 50 samples for the test set that is being compared across various models.
