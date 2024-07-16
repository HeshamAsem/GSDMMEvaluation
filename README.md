# GSDMM Evaluation Parameters
Overview
This repository contains code for calculating evaluation parameters for the Gibbs Sampling Dirichlet Multinomial Mixture (GSDMM) model. GSDMM is a clustering algorithm often used for text data to uncover latent groupings or topics within a corpus. This repository provides tools to evaluate the performance and effectiveness of the GSDMM model using various evaluation metrics.

Table of Contents
Installation
Usage
Evaluation Metrics
Examples
Contributing
License
Installation
Prerequisites
Ensure you have Python 3.6+ installed. You can download it from python.org.

Clone the Repository
bash
Copy code
git clone https://github.com/yourusername/gsdmm-evaluation.git
cd gsdmm-evaluation
Create a Virtual Environment
It is recommended to create a virtual environment to manage dependencies.

bash
Copy code
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
Install Dependencies
Install the required packages using pip:

bash
Copy code
pip install -r requirements.txt
Usage
Running the Evaluation
The main script to run the evaluation is evaluate_gsdmm.py. It takes as input the results from a GSDMM model and computes various evaluation metrics.

bash
Copy code
python evaluate_gsdmm.py --input results.json --output evaluation.json
Arguments
--input: Path to the input JSON file containing the GSDMM model results.
--output: Path to the output JSON file where evaluation results will be saved.
Evaluation Metrics
The following evaluation metrics are calculated by the code:

Perplexity: Measures how well the model predicts a sample.
Normalized Mutual Information (NMI): Measures the similarity between the clustering results and the ground truth.
Adjusted Rand Index (ARI): Evaluates the clustering performance by considering all pairs of samples and counting pairs that are assigned in the same or different clusters in the predicted and true clusterings.
Silhouette Score: Measures how similar an object is to its own cluster compared to other clusters.
Examples
Example Input JSON
The input JSON file should have the following structure:

json
Copy code
{
    "documents": ["doc1", "doc2", "doc3", ...],
    "cluster_assignments": [0, 1, 1, ...],
    "vocabulary": ["word1", "word2", "word3", ...],
    "word_counts": [[count1, count2, ...], [count1, count2, ...], ...]
}
Example Output JSON
The output JSON file will have the evaluation results:

json
Copy code
{
    "perplexity": 123.45,
    "nmi": 0.67,
    "ari": 0.78,
    "silhouette_score": 0.56
}
Contributing
Contributions are welcome! Please read the CONTRIBUTING.md for guidelines on how to contribute to this project.

License
This project is licensed under the MIT License. See the LICENSE file for details.
