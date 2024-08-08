
# Title: Textual Analysis of Online Articles

## Report

### Introduction
This report describes the implementation and results of a textual analysis performed on a series of online articles. The project involves data loading, extraction of article text from URLs, and analysis of the text for various linguistic and sentiment metrics.

### Data Loading
The analysis begins with loading a dataset containing URLs of articles. The dataset is stored in an Excel file. Using the `pandas` library, the Excel file is read into a DataFrame, which allows for easy manipulation and access to the data. Displaying the first few rows of the DataFrame helps in understanding its structure and content.

### Data Extraction
Article text is extracted from each URL using web scraping techniques. The `requests` library is used to send an HTTP request to each URL, and `BeautifulSoup` from the `bs4` library is used to parse the HTML content of the webpage. The script extracts the title and main content of the article. If the request to the URL is unsuccessful or if the article content cannot be found, the function returns `None`.

### Saving Extracted Articles
The extracted articles are saved to text files in a specified directory. The script first checks if the output directory exists and creates it if necessary. For each URL in the dataset, the article text is extracted and saved to a text file named with the corresponding URL ID. If the article text cannot be extracted, an empty file is created.

### Textual Analysis
Textual analysis is performed to calculate various metrics including word count, sentiment scores, and readability indices. This section involves several steps:

#### Dependencies
The necessary libraries are installed and imported. This includes `syllapy` for syllable counting, `textblob` for sentiment analysis, `nltk` for natural language processing, and `re` for regular expressions. Additionally, NLTK data such as tokenizers and stop words are downloaded.

#### Text Cleaning and Metric Calculation
Text is cleaned by tokenizing it into words, removing stop words, and ensuring that only alphabetic words are retained. Various metrics are calculated, including:

- **Word Count**: The total number of cleaned words.
- **Positive and Negative Scores**: The number of positive and negative words based on their sentiment polarity using `TextBlob`.
- **Polarity and Subjectivity Scores**: Calculated using the positive and negative scores.
- **Average Sentence Length**: The average number of words per sentence.
- **Complex Words and Percentage of Complex Words**: Words with three or more syllables.
- **Fog Index**: A readability index based on sentence length and the percentage of complex words.
- **Syllables per Word**: Average number of syllables per word.
- **Personal Pronouns**: Count of personal pronouns in the text.
- **Average Word Length**: Average length of words in the text.

### Analysis Results
Results of the analysis for each article are compiled into a DataFrame. Each row in the DataFrame represents an article and includes the URL ID, URL, and all calculated metrics. The results are then saved to an Excel file for easy access and further analysis.

### Conclusion
The script successfully extracts text from online articles and performs detailed textual analysis, generating various metrics that can be used for further research and insights. The results are saved to an Excel file for easy access and analysis.

### Pro tip
Execute the code in colab!!
"""
