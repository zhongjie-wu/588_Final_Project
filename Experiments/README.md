# Reproducing Experiment Results

To accurately replicate the experiment results, please follow these steps:

1. **Organize Image Folders**:
   - Relocate all folders from the "qa_pair_images" directory to the "Experiments" folder. This ensures that all image paths are correctly set up.

2. **API Key Configuration**:
   - Update the configuration files with your Bard and OpenAI API keys. Replace the existing placeholders in the configuration files with your valid API keys.

3. **Install Dependencies**:
   - Ensure that the version of Python used is >= 3.7.1.
   - Some Python packages are required for the experiment. Install them using `pip`:
     ```
     pip install bardapi bert_score rouge openai
     ```
   - `pip` will install the latest stable version of these packages. The versions for each package are also provided here:
     - `bardapi`: v0.1.38
     - `bert_score`: v0.3.13
     - `rouge`: v1.0.1
     - `openai`: v1.5.0
   - Ensure these packages are installed in your Python environment before running the experiment scripts.

By following these steps, you should be able to recreate the experiment environment and reproduce the results as documented. There isn't a specific computing specification required beyond having enough computational power to query the Bard and GPT-4V APIs and calculate the BERT and ROUGE scores.

# Files and Folders
A description of each file and folder is listed below:
* `papers.json`: A JSON file containing all papers used for the QA pairs in this experiment. The arXiv IDs serve as the key for the papers, and the title, abstract, summary, and full text are stored alongside the figures and tables.
  * Each paper's full text obtained from the LaTeX source is stored in sections.
  * Each figure and table is stored as a file path and a caption in this JSON file. 
* `questions.jsonl`: A JSON file containing the questions tested on Bard and GPT-4V. Each questions is stored alongside its answer, as well as the evidence and references primary and secondary papers used for the question.
* `qa_pair_images`: A folder containing the images used for each question. Within the main folder, there are sub-folders with the naming scheme `q_(num)`, where `num` represents the question number. 
* `Test_for_588_Report.ipynb`: A Python notebook containing the experiments run to obtain the results detailed in the final project report.
* `bard_answers_bert_score.jsonl`: A JSON file containing the generated answers from Bard to each question in the dataset. The BERT scores are also stored for each question. 
* `gpt4v_answers_bert_rouge.jsonl`: A JSON file containing the generated answers from GPT-4V to each question in the dataset. The BERT and ROUGE scores are stored for each question as well. 