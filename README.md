![Twitter Sentiment Analysis](tt.png)

# Sentiment Analysis From Scratch: A Deep Dive into Twitter Data

The digital age has revolutionized the way we communicate and express ourselves. Every day, millions of people around the globe share their thoughts, feelings, and opinions on social media platforms like Twitter. Understanding the sentiment behind these messages can be immensely valuable for businesses, governments, and individuals, as it offers insights into public perception of brands, products, policies, and more. In this context, natural language processing (NLP) techniques have become essential to extract relevant information from this unstructured data.

The primary aim of this project is to use the [Sentiment140 dataset](https://www.kaggle.com/datasets/kazanova/sentiment140?datasetId=2477&sortBy=voteCount) and Natural Language Processing (NLP) techniques to develop a model that can automatically predict the sentiment behind a tweet. By doing this, we can gain a better understanding of how people feel about different topics and use this information to make informed decisions in various areas such as marketing, product development, and public policies.

Given that this project is undertaken with an educational focus, the decision was made to build everything from scratch. This includes training custom Word2Vec models for word vectorization and designing a neural network classifier, allowing for a deep understanding of each step in the process and the intricacies involved in sentiment analysis.

---

### [About Sentiment140 dataset](https://www.kaggle.com/datasets/kazanova/sentiment140?datasetId=2477&sortBy=voteCount)

The Sentiment140 dataset is a compilation of 1.6 million tweets that have been categorized as either positive or negative. Sourced from [Kaggle](https://www.kaggle.com/datasets/kazanova/sentiment140?datasetId=2477&sortBy=voteCount), this dataset is a rich resource for those interested in sentiment analysis. Each tweet in the dataset comes with several attributes, such as:

| Column | Description |
|:---------------------:|:-------------:|
| target              | The polarity of the tweet (0 = negative, 2 = neutral, 4 = positive) |
| ids                 | The ID of the tweet (example: 2087) |
| date                | The date of the tweet (example: Sat May 16 23:58:44 UTC 2009) |
| flag                | The query (example: lyx). If there is no query, then this value is NO_QUERY |
| user                | The user who tweeted (example: robotickilldozr) |
| text                | The text of the tweet (example: Lyx is cool) |


---

# Project Workflow and Notebook Breakdown

The project is divided into three notebooks:
### • [Data Visualization and Cleaning:](https://github.com/lucasaltm/Twitter_Sentiment_Analysis/blob/main/TSA1_Data_Cleaning.ipynb)
In this initial notebook, the focus lies on preparing and cleaning the data for sentiment analysis. The journey starts with an initial visualization of the data, offering a clear understanding of the dataset before any processing is undertaken. This is followed by a rigorous text pre-processing and cleaning process, which involves:

- Removing irrelevant words, known as "stop-words".
- Eliminating punctuation and accented characters.
- Applying "stemming" to reduce words to their root form.
- Excluding non-alphabetic characters.

After these steps, the notebook presents a view of the most frequent words, giving an insight into the nature of the content post-cleaning. Finally, the cleaned and processed data is saved in a CSV format, setting the stage for the subsequent stages of the project which involve modeling and analysis.

### • [Word Vectorization:](https://github.com/lucasaltm/Twitter_Sentiment_Analysis/blob/main/TSA2_Vectorization.ipynb)

In the vast world of Natural Language Processing (NLP), transforming textual data into a numerical format is a foundational step. This notebook delves deep into the vectorization aspect of the sentiment analysis project, turning raw tweet text into vectors that can be fed into machine learning algorithms.

The journey begins with the preparation of the dataset, splitting it into training and testing sets, ensuring a robust evaluation process. Following this, several vectorization techniques are explored, each with its unique approach and advantages:

**CountVectorizer:** A simple yet effective method that transforms the text into vectors based on word count.

**TF-IDF Vectorizer:** Going a step beyond mere counting, this method weighs terms based on their importance in the corpus, distinguishing between common and rare terms.

**Word2Vec:** A more advanced technique that captures the semantic meaning of words based on their context. Both Skip-Gram and CBOW models are explored to achieve this

Additionally, a logistic regression model is trained and evaluated as a preliminary step to gauge the effectiveness of the vectorized data. This notebook sets the stage for subsequent modeling and deep analysis, ensuring the data is well-prepared and understood.

### • [Neural Network Modeling:](https://github.com/lucasaltm/Twitter_Sentiment_Analysis/blob/main/TSA3_NN.ipynb)

In this notebook, the focus is on the construction, training, and evaluation of neural networks for sentiment classification. Three different neural network architectures (Basic Feedforward, Long Short-Term Memory (LSTM), and Gated Recurrent Units (GRU)) are systematically trained and tested. Various hyperparameters for each architecture are also explored to identify the most effective combination for sentiment analysis. To validate the observed performance differences among these architectures, rigorous statistical tests like ANOVA, t-tests, Kruskal-Wallis, and Mann-Whitney are conducted. Vectorization methods trained in the previous notebook are used to prepare the data. To ensure transparency and reproducibility, MLflow is employed as a central tracking tool, capturing details, metrics, and outcomes of each model iteration.
