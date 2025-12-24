# Système de Recommandation de Livres avec LLMs

## Vue d'ensemble
Ce projet cartographie le paysage littéraire en utilisant des **Grands Modèles de Langage (LLMs)** et la **Recherche Vectorielle** pour construire un système intelligent de recommandation de livres. Contrairement au filtrage collaboratif traditionnel, ce système exploite la signification sémantique des descriptions de livres pour trouver des recommandations pertinentes, effectuer une classification et analyser le ton émotionnel.

## Fonctionnalités
- **Recherche Vectorielle Sémantique** : Utilise les embeddings OpenAI et ChromaDB pour trouver des livres avec des thèmes ou des intrigues similaires basés sur des requêtes en langage naturel.
- **Analyse des Émotions** : Analyse l'arc émotionnel des descriptions de livres en utilisant un modèle DistilRoBERTa pour quantifier les sentiments (Joie, Peur, Surréalisme, etc.).
- **Classification Zéro-Shot** : Catégorise les livres dans des genres sans données d'entraînement explicites en utilisant des techniques d'apprentissage zéro-shot.
- **Exploration de Données** : Analyse Exploratoire de Données (EDA) complète sur le jeu de données de livres.

## Structure du Projet
- `vector-search.ipynb` : Le moteur de recommandation principal. Il gère le découpage du texte, la génération d'embeddings avec OpenAI et le stockage dans une base de données vectorielle Chroma pour la récupération.
- `sentimests_classifications.ipynb` : Effectue une analyse des sentiments sur les descriptions de livres pour étiqueter les livres avec des profils émotionnels.
- `zero_shot_classification_model.ipynb` : Utilise la classification zéro-shot pour explorer et affiner les catégories de livres.
- `data-exploration.ipynb` : Notebook pour le nettoyage initial des données, la visualisation et la compréhension des statistiques du jeu de données.
- `dashboard.py` : (En Construction) Espace réservé pour une interface utilisateur basée sur Streamlit pour interagir avec le système de recommandation.
- `books_cleaned.csv` : Le jeu de données traité utilisé pour l'analyse et la modélisation.

## Technologies Utilisées
- **Python**
- **LangChain** : Pour orchestrer les workflows LLM et les interactions avec le stockage vectoriel.
- **OpenAI API** : Pour générer des embeddings de texte de haute qualité.
- **ChromaDB** : Pour un stockage vectoriel efficace et une recherche de similarité.
- **Hugging Face Transformers** : Pour les pipelines d'analyse des sentiments et de classification zéro-shot.
- **Pandas & NumPy** : Pour la manipulation de données.
- **Streamlit** (Prévu) : Pour le tableau de bord web.

## Installation et Configuration

1. **Cloner le dépôt**
   ```bash
   git clone <url_du_dépôt>
   cd Book-Recommender-System-with-LLMs
   ```

2. **Installer les Dépendances**
   Assurez-vous d'avoir Python installé. Vous pouvez installer les bibliothèques nécessaires en utilisant pip :
   ```bash
   pip install pandas numpy langchain langchain-community langchain-openai langchain-chroma transformers tqdm python-dotenv notebook
   ```

3. **Variables d'Environnement**
   Créez un fichier `.env` dans le répertoire racine et ajoutez votre clé API OpenAI :
   ```
   OPENAI_API_KEY=votre_clé_api_ici
   ```

## Utilisation
1. **Lancer les Notebooks** : Démarrez Jupyter Notebook pour explorer les modèles et la logique.
   ```bash
   jupyter notebook
   ```
   - Commencez par `data-exploration.ipynb` pour comprendre les données.
   - Exécutez `vector-search.ipynb` pour construire l'index vectoriel et interroger des recommandations.
   - Exécutez `sentimests_classifications.ipynb` pour voir l'analyse des émotions en action.

2. **Tableau de Bord** : (Bientôt disponible)
   Une fois implémenté, le tableau de bord pourra être lancé via :
   ```bash
   streamlit run dashboard.py
   ```

## Travaux Futurs
- Implémenter le tableau de bord interactif Streamlit.
- Intégrer les scores émotionnels dans la logique de classement des recommandations.
- Étendre le jeu de données pour inclure des genres plus diversifiés.

---

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