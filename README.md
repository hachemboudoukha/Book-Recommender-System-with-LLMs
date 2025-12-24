# Book Recommender System with LLMs

## Overview
This project maps the landscape of literature using **Large Language Models (LLMs)** and **Vector Search** to build an intelligent Book Recommender System. Unlike traditional collaborative filtering, this system leverages the semantic meaning of book descriptions to find relevant recommendations, classification, and emotional tone.

## Features
- **Semantic Vector Search**: Uses OpenAI embeddings and ChromaDB to find books with similar themes or plots based on natural language queries.
- **Emotion Analysis**: Analyzes the emotional arc of book descriptions using a DistilRoBERTa model to quantify sentiments (Joy, Fear, Surrealism, etc.).
- **Zero-Shot Classification**: Categorizes books into genres without explicit training data using zero-shot learning techniques.
- **Data Exploration**: Comprehensive Exploratory Data Analysis (EDA) on the book dataset.

## Project Structure
- `vector-search.ipynb`: The core recommendation engine. It handles text chunking, embedding generation using OpenAI, and storage in a Chroma vector database for retrieval.
- `sentimests_classifications.ipynb`: Performs sentiment analysis on book descriptions to tag books with emotional profiles.
- `zero_shot_classification_model.ipynb`: Uses zero-shot classification to explore and refine book categories.
- `data-exploration.ipynb`: Notebook for initial data cleaning, visualization, and understanding the dataset statistics.
- `dashboard.py`: (Under Construction) Placeholder for a Streamlit-based user interface to interact with the recommender system.
- `books_cleaned.csv`: The processed dataset used for analysis and modeling.

## Technologies Used
- **Python**
- **LangChain**: For orchestrating LLM workflows and vector store interactions.
- **OpenAI API**: For generating high-quality text embeddings.
- **ChromaDB**: For efficient vector storage and similarity search.
- **Hugging Face Transformers**: For sentiment analysis and zero-shot classification pipelines.
- **Pandas & NumPy**: For data manipulation.
- **Streamlit** (Planned): For the web dashboard.

## Setup and Installation

1. **Clone the repository**
   ```bash
   git clone <repository_url>
   cd Book-Recommender-System-with-LLMs
   ```

2. **Install Dependencies**
   Ensure you have Python installed. You can install the necessary libraries using pip:
   ```bash
   pip install pandas numpy langchain langchain-community langchain-openai langchain-chroma transformers tqdm python-dotenv notebook
   ```

3. **Environment Variables**
   Create a `.env` file in the root directory and add your OpenAI API key:
   ```
   OPENAI_API_KEY=your_api_key_here
   ```

## Usage
1. **Run the Notebooks**: Start Jupyter Notebook to explore the models and logic.
   ```bash
   jupyter notebook
   ```
   - Start with `data-exploration.ipynb` to understand the data.
   - Run `vector-search.ipynb` to build the vector index and query recommendations.
   - Run `sentimests_classifications.ipynb` to see the emotion analysis in action.

2. **Dashboard**: (Coming Soon)
   Once implemented, the dashboard can be launched via:
   ```bash
   streamlit run dashboard.py
   ```

## Future Work
- Implement the interactive Streamlit dashboard.
- Integrate the emotion scores into the recommendation ranking logic.
- Expand the dataset to include more diverse genres.