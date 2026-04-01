# Amazon-Product-Reviews-Sentiment-Analysis
This project analyzes Amazon product reviews to uncover patterns in customer satisfaction across product categories, detect inconsistencies between written sentiment and star ratings, and generate practical business recommendations for sellers. The analysis combines lexicon-based and transformer-based sentiment models.

The analysis combines lexicon-based and transformer-based sentiment models to compare how well different approaches capture real customer opinions.

The study was carried out on 28,262 Amazon product reviews collected between 2009 and 2019. After data cleaning and category correction, the final analysis focused on four product groups:
- Electronics
- Health & Beauty
- Toys & Games
- Office Supplies
- Problem Statement
How can sentiment analysis of Amazon consumer reviews be used to uncover patterns in customer satisfaction across product categories, identify rating inconsistencies, and generate actionable business recommendations for sellers?

**Objectives**
The main objectives of this project were to:
analyze customer sentiment in Amazon reviews
compare sentiment patterns across product categories
identify mismatches between review text and star ratings
compare the performance of VADER and RoBERTa
generate business insights for product sellers and platform decision-makers

**Dataset**
The dataset contains Amazon customer reviews, including:
review text
star ratings
product category
review date
A key preprocessing step involved correcting 6,177 miscategorised reviews, where battery-related products had been incorrectly labelled under Health & Beauty. After cleaning, only statistically meaningful categories and time periods were retained.

**Methodology**
1. Data Cleaning and Preparation
The dataset was first cleaned to improve analysis quality. This included:
removing irrelevant or statistically insignificant periods
correcting category labelling issues
retaining the most reliable product groups
preparing review text for sentiment classification
2. Sentiment Analysis Models
Two sentiment analysis approaches were used:

**VADER**

a lexicon and rule-based sentiment analysis tool
useful for fast baseline sentiment scoring
works well on simple emotional wording, but struggles with context

**RoBERTa**
a transformer-based NLP model
captures context more effectively than lexicon-based approaches
better suited to reviews containing mixed opinions, subtle criticism, or sarcasm-like phrasing

3. Comparative Analysis
The project compared:
sentiment distribution across categories
agreement between VADER and RoBERTa
alignment between sentiment labels and review star ratings
examples of model disagreement for interpretation

**Key Findings
**Overall Sentiment Distribution
Using RoBERTa, the review sentiment distribution was:
Positive: 23,682
Neutral: 2,345
Negative: 2,235
This suggests that most reviews in the dataset were positive, but a meaningful number of reviews contained neutral or negative experiences.
Category-Level Insight
Category comparison revealed that customer satisfaction was not evenly distributed across product groups. For example, Office Supplies emerged as one of the strongest-performing categories in sentiment terms, showing consistently high positive sentiment.

**VADER vs RoBERTa
The comparison showed that RoBERTa performed better than VADER, especially on negative reviews.
For low-rated reviews:
RoBERTa correctly identified 1,247 out of 1,575 negative reviews
VADER correctly identified only 807 out of 1,575
One important issue was that VADER incorrectly labelled many clearly negative reviews as positive, showing its weakness in interpreting context-heavy or politely worded dissatisfaction.

**Model Agreement
Out of 28,262 reviews, 3,951 reviews (14.0%) were classified differently by VADER and RoBERTa.
This means the models agreed on about 86% of cases overall, but the disagreement analysis showed that the main area of confusion was the boundary between neutral and positive reviews. More concerning were cases where one model predicted positive and the other predicted negative, showing how difficult real-world review language can be.

**Rating Inconsistencies
By comparing sentiment labels with star ratings, the project found that star ratings alone are not always a reliable representation of review sentiment. Some reviews had high ratings but included negative language, while others had lower ratings with mixed or balanced text. This highlights the value of text-based sentiment analysis alongside numeric ratings.

**Business Recommendations
Based on the findings, the project suggests that sellers and platforms should:
use transformer-based sentiment models such as RoBERTa for more accurate review analysis
not rely only on star ratings when assessing customer satisfaction
monitor category-level sentiment trends to identify stronger and weaker product segments
pay close attention to mixed and neutral reviews, as these often contain useful improvement signals
investigate negative-text/high-rating mismatches because they may reveal hidden customer dissatisfaction

**Tools and Technologies
This project was developed using Python and common data science libraries for text analysis and visualization, likely including:
Python
pandas
matplotlib / seaborn
VADER
Hugging Face transformers
RoBERTa

**Project Structure
A typical structure for this project may look like this:
├── data/
├── notebooks/
│   └── Social_Media_Analytics_Amazon_Analysis.ipynb
├── outputs/
│   ├── charts/
│   └── tables/
├── README.md
└── requirements.txt

