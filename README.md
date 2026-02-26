# 🎬 Netflix Movies & TV Shows Clustering

![Netflix Interface](Netflix_Interface.png)
**Unsupervised NLP-Based Content Grouping & Recommendation Engine**

## 📌 Project Overview
This project builds a content-based clustering and recommendation framework for Netflix titles using unsupervised machine learning and Natural Language Processing (NLP). The core objective is to uncover semantic similarity structures within Netflix's catalog to group similar titles based on textual metadata such as descriptions, genres, cast, and directors.

## 🎯 Business Objective
With thousands of titles available, content discovery is a major challenge for streaming platforms. This project aims to:
- **Segment the Catalog:** Use unsupervised learning to group content into meaningful semantic clusters.
- **Enhance Personalization:** Build a content-based recommendation system to improve user navigation.
- **Similarity Mapping:** Identify hidden relationships between international content and mainstream genres based on narrative themes.

## 📊 Dataset Insights
- **Source:** Kaggle (7,787 titles × 11 features)
- **Composition:** 69% Movies and 31% TV Shows
- **Top Producers:** US, India, and UK dominate content volume
- **Trends:** 2018 saw the peak of content additions; TV-MA is the most frequent rating in the catalog

## ⚙️ Machine Learning Pipeline

### 1. Preprocessing & Feature Engineering
- **Unified Tags:** Combined `Description`, `Genre`, `Cast`, `Country`, `Director`, and `Rating` into a single textual feature string to capture multi-dimensional context.
- **Text Cleaning:** Implemented lowercasing, stopword removal, punctuation cleaning, and Snowball Stemming to reduce words to their root form.

### 2. Vectorization & Dimensionality Reduction
- **TF-IDF:** Converted text into a high-dimensional numerical feature space (10,000 features), weighting terms by their relative importance.
- **PCA:** Reduced the feature space to 3,000 components to capture 80%+ of the total variance, significantly reducing sparsity and computational overhead while preserving the dataset's core information.

### 3. Clustering Algorithms

| Algorithm | Selection Method | Result |
|---|---|---|
| K-Means | Elbow Method & Silhouette Score | Best Silhouette at k=2 |
| Agglomerative | Dendrogram (Ward Linkage) | 7 Clusters |

### 4. Recommendation Engine
Developed a similarity-based retrieval system that computes cosine similarity between TF-IDF vectors. By measuring the angular similarity between the query title and the rest of the catalog, the engine returns the **Top 10 most semantically related titles**.

## 🏁 Results & Conclusion
- **Meaningful Segmentation:** The clustering algorithms successfully identified distinct content categories, such as "International Dramas," "US-based Comedies," and "Documentaries," as validated by WordCloud analysis of the cluster-specific keywords.
- **Relevant Recommendations:** The recommendation engine demonstrates relevant similarity-based suggestions, effectively grouping content with shared thematic elements (e.g., matching gritty international thrillers with similar crime dramas).
- **Final Takeaway:** By combining NLP with unsupervised learning, this project demonstrates how raw metadata can be transformed into an organized system that powers content discovery and enhances the user experience.


## 🛠️ Tech Stack
- **Language:** Python
- **Data Handling:** `pandas`, `numpy`
- **ML/NLP:** `scikit-learn`, `nltk`, `scipy`
- **Visualization:** `matplotlib`, `seaborn`, `wordcloud`

## 👤 Author
**JAYAKRISHNAN K**
