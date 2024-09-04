
# Zero-Shot Text Classification

This project demonstrates how to perform zero-shot text classification using the Hugging Face `transformers` library. Zero-shot classification allows you to classify text into categories that were not present during the model's training, making it a powerful tool for flexible and dynamic text classification tasks.

## Getting Started

### Prerequisites

Ensure you have the following installed:

- Python 3.7 or higher
- Hugging Face `transformers` library

You can install the required library using pip:

```bash
pip install transformers
```

### Code Overview

This project uses the `facebook/bart-large-mnli` model, a variant of the BART model fine-tuned on the Multi-Genre Natural Language Inference (MNLI) dataset.

### How to Use

1. **Load the Model:**

   The model is loaded using the `pipeline` function from the `transformers` library. The `zero-shot-classification` pipeline is used, which allows for classifying text against a set of candidate labels.

2. **Input Text and Labels:**

   The text sequence to classify and the candidate labels are defined as:

   ```python
   sequence_to_classify = "I'm going to bake a cake"
   candidate_labels = ["shopping", "cooking", "driving", "travel"]
   ```

3. **Perform Classification:**

   The classification is done by passing the text and labels to the model:

   ```python
   result = classifier(sequence_to_classify, candidate_labels)
   ```

4. **Output:**

   The result will display the classification scores for each label, indicating the model's confidence that the input text belongs to each category.

   ```python
   print(result)
   ```

### Example Output

```python
{
   'sequence': "I'm going to bake a cake",
   'labels': ['cooking', 'shopping', 'travel', 'driving'],
   'scores': [0.95, 0.02, 0.02, 0.01]
}
```

In this example, the model is highly confident that the text "I'm going to bake a cake" is related to "cooking."

## Acknowledgments

- [Hugging Face Transformers](https://huggingface.co/transformers/) - For providing the pre-trained models and tools for NLP tasks.
