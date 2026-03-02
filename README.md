Emotion Recognition from Text

Project Overview
This repository contains the code and technical report for a comparative study on Zero-Shot Cross-Lingual Emotion Transfer. The project evaluates how well machine learning models can learn emotional boundaries exclusively from English text and transfer that knowledge to classify Indonesian text. It directly compares a static baseline (FastText + MUSE) against a contextual architecture (mBERT).

Included Files
NLP_Project_Emotion_Recognition.ipynb: The primary Jupyter Notebook containing the complete, end-to-end Python pipeline (data downloading, preprocessing, training, evaluation, and inference).

NLP_Project_Report.pdf: The technical report detailing the methodology, hardware challenges, comparative metrics, and ethical considerations.

Datasets
Both datasets are mapped to the 6 universal Ekman emotions (Joy, Anger, Sadness, Fear, Disgust, Surprise).

Training Data (English): GoEmotions (Google Research)

Evaluation Data (Indonesian): BRIGHTER-emotion-categories

Environment & Tools
Environment: Google Colab (Runtime Type: Python 3, Python 3.12.12, Compute: T4 GPU / CPU)

Deep Learning: PyTorch (torch)

Transformers: Hugging Face transformers and datasets

Static Embeddings: gensim (MUSE vectors)

Classification: scikit-learn

Data Handling: pandas, numpy

Instructions to Run the Code
We highly recommend running this code within Google Colab to avoid local dependency issues and leverage GPU acceleration.

Step 1: Environment Setup

Upload the NLP_Project_Emotion_Recognition.ipynb file to Google Colab.

Navigate to the top menu and select Runtime > Change runtime type.

Ensure the Runtime type is set to Python 3.

Under Hardware accelerator, select T4 GPU.
(Note: The code features a dynamic resource detection script. On a T4 GPU, it processes 7,500 sentences in ~7 to 8 minutes. On a standard CPU, it triggers a safety protocol and downscales to 112 sentences to prevent crashing, taking ~16.5 minutes).

Step 2: Installing Libraries
You do not need to manually install any libraries. The very first line of the notebook contains an automated installation command (!pip install -q transformers...) that handles all dependencies.

Step 3: Executing the Pipeline
The entire pipeline has been consolidated into a single code cell for seamless execution.

Click into the single code cell.

Click the "Play" button on the left side of the cell (or press Shift + Enter).

The script will automatically execute sequentially: downloading the data, aligning the FastText baseline, fine-tuning the mBERT model, printing the metrics, and running a single-sample Indonesian prediction test.