# 💬 YouTube Comment Analysis on AI in Education — Text Mining

## 📌 Project Overview

This project analyzes YouTube comments discussing the use of Artificial Intelligence (AI) in education using Text Mining and Natural Language Processing (NLP) techniques.

The analysis combines text preprocessing, TF-IDF, Sentence-BERT, K-Means clustering, persona analysis, and Latent Dirichlet Allocation (LDA) to explore public perceptions and recurring discussion topics related to AI in education.

## 🎯 Project Objectives

- Collect YouTube comments from selected videos discussing AI in education.
- Clean and preprocess comment text for analysis.
- Compare TF-IDF and Sentence-BERT text representations.
- Apply K-Means clustering to group similar comments.
- Interpret the resulting clusters through persona analysis.
- Extract recurring discussion themes using LDA.
- Compare insights obtained from clustering and topic extraction.

## 📂 Dataset

The dataset contains **580 comment records** collected from six selected YouTube videos.

| Attribute | Description |
|---|---|
| Total records | 580 |
| Data source | YouTube |
| Number of videos | 6 |
| `video` | Source video URL |
| `comment` | Comment text |
| `likes` | Number of votes or likes reported by the downloader |
| `reply` | Number of replies |
| `time` | Comment timestamp or relative time information |

The original dataset contains duplicate comments and missing values in the `reply` column. These are addressed during preprocessing.

## 🕸️ Web Scraping

YouTube comments were collected using the `youtube-comment-downloader` Python library.

The notebook defines six YouTube video URLs and retrieves available comments from each video. The collected information is stored in a Pandas DataFrame and exported as `dataset2.csv`.

### 🔄 Scraping Workflow

1. Define the selected YouTube video URLs.
2. Initialize `YoutubeCommentDownloader`.
3. Retrieve available comments from each video.
4. Extract the video URL, comment text, likes, reply count, and time information.
5. Combine the collected records into a single DataFrame.
6. Export the dataset to a CSV file for further analysis.

The final CSV used in the analysis contains 580 records. The number of records retrieved may vary if the scraping process is executed again.

## 🧹 Text Preprocessing

The notebook prepares the comment text for analysis through several steps:

- Selecting the comment text column.
- Removing missing and duplicate comments.
- Converting text to lowercase.
- Cleaning URLs, mentions, numbers, and punctuation.
- Filtering short comments.
- Removing Indonesian stopwords and custom stopwords.
- Applying Indonesian stemming using Sastrawi.

The cleaned comments are then used for feature extraction and semantic representation.

## ⚙️ Features

- YouTube comment scraping.
- Text cleaning and preprocessing.
- TF-IDF feature extraction.
- Sentence-BERT semantic embeddings.
- K-Means clustering for different values of K.
- Silhouette Score comparison.
- Cluster-based persona analysis.
- LDA topic extraction.
- Comparison between clustering results and extracted topics.

## 🛠️ Technologies Used

- Python
- Pandas and NumPy
- Scikit-learn
- NLTK
- Sastrawi
- Sentence-Transformers
- Gensim
- Matplotlib
- `youtube-comment-downloader`

## 📊 Analysis and Results

### 1️⃣ Text Representation Comparison

The project compares two approaches for representing text:

- **TF-IDF:** Represents comments based on the importance of individual words within the dataset.
- **Sentence-BERT:** Generates semantic embeddings designed to capture contextual meaning.

According to the notebook's comparison, Sentence-BERT achieves higher Silhouette Scores than TF-IDF across the tested cluster counts.

### 2️⃣ K-Means Clustering

K-Means is evaluated using cluster counts ranging from K = 2 to K = 9. The notebook selects **K = 2**, with a reported maximum Silhouette Score of **0.074** using Sentence-BERT.

The resulting clusters are interpreted as follows:

- **Cluster 0 — Positive Perceptions:** Comments generally describe AI as a learning assistant that helps students understand educational material. Some comments also emphasize that AI should support rather than replace teachers.
- **Cluster 1 — Cautious, Skeptical, or Neutral Perceptions:** Comments raise concerns about dependence on AI, reduced critical thinking, and potential effects on student learning. This cluster also contains neutral comments.

These interpretations are based on the sampled comments in each cluster and do not represent verified demographic personas.

### 3️⃣ Persona Analysis

The notebook examines example comments from each cluster to interpret the dominant perspectives.

This qualitative analysis helps explain the patterns found by K-Means beyond the numerical clustering results.

### 4️⃣ Topic Extraction Using LDA

Latent Dirichlet Allocation (LDA) is used to identify recurring themes in the comment dataset. The notebook explores models with two, three, and four topics.

The two main themes discussed in the notebook's interpretation are:

- **Topic 1 — AI as a Learning Assistant:** Discussions about using AI to support teaching and learning without fully replacing teachers.
- **Topic 2 — AI's Impact on Learning:** Discussions about technology dependence and the possible influence of AI on students' thinking and learning processes.

### 5️⃣ Key Findings

The analysis provides two complementary perspectives:

- **Clustering** groups comments according to similarities in their text representations and helps explore different perception groups.
- **Topic Extraction** identifies recurring themes in the language used by commenters.

The results suggest that discussions about AI in education include both its potential as a learning aid and concerns about its effects on the learning process.

The reported Silhouette Score of 0.074 is relatively low, so the cluster separation should be interpreted cautiously.

## 📂 Project Structure

```text
youtube-comment-ai-education-analysis/
├── README.md
├── youtube comment analysis.ipynb
└── dataset2.csv
```

The notebook may generate additional processed data during execution. Include any generated files in the repository only if they are intended to be shared, and update this structure to match the actual uploaded files.

## 🚀 How to Run

1. Clone or download this repository.
2. Open `youtube comment analysis.ipynb` in Jupyter Notebook or Google Colab.
3. Install the required Python libraries.
4. Load `dataset2.csv`.
5. Execute the text preprocessing cells.
6. Generate TF-IDF features and Sentence-BERT embeddings.
7. Run K-Means clustering and compare the Silhouette Scores.
8. Review the cluster interpretations and LDA topic extraction results.

To repeat the data collection process, run the scraping section of the notebook and ensure the required library is installed.

## 👩‍💻 Author
**Amanda Sugito**

Text Mining academic project at BINUS University.

## 🔗 Connect with Me
- LinkedIn: Amanda Sugito | www.linkedin.com/in/amanda-sugito
- GitHub: amandasugito | https://github.com/amandasugito

## ⚠️ Disclaimer

This project was developed for academic and educational purposes as part of a Text Mining study.

The clustering results and extracted topics are exploratory interpretations of the collected YouTube comments. They do not necessarily represent the opinions of all YouTube users or the general public.

The dataset is limited to comments collected from six selected videos and may contain sampling bias. The original comments belong to their respective authors and remain subject to the applicable platform terms and policies.
