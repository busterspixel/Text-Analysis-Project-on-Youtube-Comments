# YouTube Comment Analyzer 🚀

Ever wondered what your audience *really* thinks? This project is a deep-dive analysis tool for YouTube comments. It moves beyond simple word counts to uncover viewer sentiment, recurring topics, and common phrases, helping you get a true sense of your community's feedback.

Whether you're a content creator trying to understand your audience, a marketer gauging campaign reception, or just a data enthusiast curious about online communities, this script helps you make sense of the noise.



## What's Inside? 🛠️

This script is an end-to-end pipeline that takes a raw export of YouTube comments and turns it into actionable insights.

* **Cleans Up the Mess (Preprocessing)**: Comments are messy. The script automatically handles things like converting text to lowercase, removing punctuation and special characters, and filtering out common "stopwords" (like 'the', 'a', 'is') to focus on what matters.

* **Reads the Vibe (Sentiment Analysis)**: It analyzes each comment to determine if the sentiment is **Positive**, **Negative**, or **Neutral**. This gives you a high-level view of the overall audience reaction.

* **Finds the Hot Topics (Topic Modeling)**: What are people actually talking about? The script uses machine learning (NMF) to discover the main themes or topics hidden in the comments. You might find topics related to the video's subject, the host, production quality, or suggestions for future content.

* **Spots Common Phrases (N-gram Analysis)**: It identifies frequently used two-word (**bigrams**) and three-word (**trigrams**) phrases. This is great for spotting memes, repeated questions, or specific feedback that many people are giving.

* **Paints a Picture (Visualization)**: Data is great, but visuals are better. The script generates several plots to help you understand the results at a glance:
    * A **pie chart** for the sentiment breakdown.
    * **Bar charts** and **word clouds** for each discovered topic.

## Getting Started ⚙️

You don't need to be a data scientist to use this. Just follow these steps.

### 1. Prerequisites

Make sure you have **Python 3** installed on your machine.

### 2. Install the Libraries

Open your terminal or command prompt and install the necessary Python packages with this one command:

```bash
pip install pandas openpyxl nltk textblob scikit-learn matplotlib wordcloud
```

The first time you run the script, it will also download some essential data from `nltk` (`punkt` and `stopwords`). Just let it do its thing.

### 3. Add Your Data

* Get your YouTube comments into an Excel (`.xlsx`) file.
* Make sure the column containing the comment text is named **`comment`**.
* Place this file in the same folder as the script.
* Open the script and change the `file_path` to your file's name.

```python
# Change this line to point to your Excel file
file_path = (r"D:\GVA PIGM\dataset_youtube-comments-scraper_2025-08-23_09-09-29-554.xlsx")
```

### 4. Run the Script!

Execute the Python script from your terminal:
```bash
python your_script_name.py
```

Sit back and let it run. It will print its progress and the final results to the console, and the charts will pop up on your screen.

## What You Get (The Output) 📈

After the script finishes, you'll have a few new things:

1.  **New Excel Files**:
    * `ytp3.xlsx`: Contains the original comments along with all the cleaned and processed text.
    * `sentiment_analysis_resultsytp3.xlsx`: The main output file! This includes the final sentiment scores, categories, and the cleaned text for every comment.

2.  **Console Output**:
    * The top words for each of the 5 topics discovered.
    * A list of the top 20 most common bigrams and trigrams.

3.  **Visualizations**:
    * A pie chart showing the sentiment distribution.
    * Bar charts and beautiful word clouds for each topic, making it easy to see what each theme is about.
