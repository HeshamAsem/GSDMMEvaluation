# GSDMM Evaluation

This repository provides an implementation of the Gibbs Sampling Dirichlet Mixture Model (GSDMM) and tools for evaluating its performance. The GSDMM algorithm is designed to identify clusters in short texts, such as tweets or forum posts.

## Features

- **GSDMM Implementation**: Core algorithm to perform clustering on short text data.
- **Evaluation Metrics**: Tools to evaluate the clustering performance using various metrics.
- **Preprocessing Utilities**: Functions to preprocess text data before clustering.

## Getting Started

### Prerequisites

To run this project, you need Python 3.7+ and the following Python libraries:

- numpy
- pandas
- scikit-learn
- nltk
- tqdm

You can install these dependencies using `pip`:

```bash
pip install numpy pandas scikit-learn nltk tqdm
```

### Installation

1. Clone the repository:

```bash
git clone https://github.com/HeshamAsem/GSDMMEvaluation.git
```

2. Navigate to the project directory:

```bash
cd GSDMMEvaluation
```

3. Install the required packages:

```bash
pip install -r requirements.txt
```

### Usage

1. **Data Preparation**: Prepare your dataset as a CSV file with a column for text data. An example dataset is provided in the `data` directory.

2. **Running the GSDMM Algorithm**:

```python
from gsdmm import MovieGroupProcess

# Example data
texts = ["text1", "text2", "text3"]

# Preprocess texts (tokenization, stop word removal, etc.)
# ...

# Initialize the GSDMM model
mgp = MovieGroupProcess(K=10, alpha=0.1, beta=0.1, n_iters=30)

# Fit the model to the texts
vocab = set(word for text in texts for word in text)
n_terms = len(vocab)
doc_term_matrix = [[text.count(word) for word in vocab] for text in texts]

y = mgp.fit(doc_term_matrix, n_terms)
```

3. **Evaluating the Clustering Performance**:

```python
from evaluation import evaluate

# Evaluate the clustering result
metrics = evaluate(true_labels, predicted_labels)
print(metrics)
```

### Examples

Check the `examples` directory for Jupyter notebooks demonstrating how to use the GSDMM implementation and evaluate its performance on sample datasets.

## Project Structure

- `gsdmm`: Contains the implementation of the GSDMM algorithm.
- `evaluation`: Contains tools for evaluating the clustering performance.
- `data`: Directory for storing datasets.
- `examples`: Jupyter notebooks with example usage.
- `requirements.txt`: List of required Python packages.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

### Steps to Contribute

1. Fork the repository.
2. Create a new branch: `git checkout -b feature-branch`
3. Commit your changes: `git commit -m 'Add new feature'`
4. Push to the branch: `git push origin feature-branch`
5. Open a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

This project is based on the work by Hesham Abdelmotaleb, University of Plymouth, under supervision of Dr Malgorzata Wjoyts, and Dr Craig Mcneile. Special thanks to the authors of the original GSDMM algorithm.

## Contact

For any questions or inquiries, please contact [Hesham Asem](https://github.com/HeshamAsem).

---

Happy Clustering! 🚀
