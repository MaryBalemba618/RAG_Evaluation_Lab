# RAG_Evaluation_Lab
Vertex AI RAG evaluation lab and results
# Evaluate RAG Systems with Vertex AI

## Purpose
This lab evaluates whether RAG answers are relevant, helpful, and
supported by the provided context. It compares two sets of answers
using Vertex AI's Gen AI Evaluation Service.

## Tools
- Google Cloud Vertex AI
- Vertex AI Workbench and JupyterLab
- Python and pandas
- Vertex AI Gen AI Evaluation Service
- Vertex AI Experiments

## Confirmed Results

| Answer Set | Groundedness Mean |
|---|---:|
| Model A | 0.667 |
| Model B | 0.000 |

Both reference-free evaluation runs completed and were saved in
Vertex AI Experiments under `rag-eval-01`.

These results cover three examples. They do not establish
production reliability.

## Files
- RAG_Evaluation_Lab.ipynb: Notebook code and saved outputs.
- model_a_details.csv: Detailed results for Model A.
- model_b_details.csv: Detailed results for Model B.
- evaluation_summary.csv: Summary comparison.
- experiment_results.png: Evidence of completed experiment runs.

## How to Run
1. Use a Google Cloud project with billing and the Vertex AI API enabled.
2. Give the notebook's runtime identity the required evaluation and
   experiment permissions.
3. Open the notebook in Vertex AI Workbench.
4. Install the required packages and restart the kernel after installation.
5. Set your own project ID and supported location.
6. Run the setup, dataset, custom-metric, and evaluation cells in order.
7. Keep experiment logging enabled to save runs in Vertex AI Experiments.
8. Review the scores and individual explanations.

Do not restart the kernel between dependent cells unless you plan
to rerun the earlier setup cells.

## Troubleshooting
I encountered missing-variable errors involving EXPERIMENT, the
datasets, and evaluation tasks, as well as a missing pandas import.
I resolved these by running the required cells in order and using
consistent variable names.

I also encountered IAM permission errors when accessing and creating
the metadata store. After addressing the notebook account's access,
both evaluation runs completed with experiment logging enabled.

## Interpretation
Model A showed better grounding than Model B, but it still produced
an unsupported answer. This demonstrates why clear wording alone
does not make an answer trustworthy.

Source validation, more test cases, and review of unsupported claims
would be needed before considering production use. Grounding alone
does not establish protection against poisoned source documents.

## Completion Status
Reference-free evaluation is confirmed complete.
Reference-based evaluation results should be added once completed.

## Lab Source
https://codelabs.developers.google.com/codelabs/production-ready-ai-with-gc/6-ai-evaluation/evaluate-rag-systems-with-vertex-ai
