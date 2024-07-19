# DigDeeper: Enhancing Scholarly Article Recommendations
This project was done as a capstone project for The Data Incubator Fellowship program.

# Background:

Researchers spend approximately 23% of their total work time reading around 22 scholarly articles per month. The reasons for reading these articles vary, including staying updated with research progress in their field, generating new research ideas, and garnering support for their research views and results.

 How to Find Scholarly Articles to Read:
 
 Traditional Methods:
1. Searching using keywords
2. Scanning current and previous issues of top journals in their field
3. Article recommendations from colleagues
4. Using other tools such as CONNECTED PAPERS

The traditional methods often rely on a single article for generating recommendations, recommend a single article, or rely on just a few keywords. These solutions may not be very useful for researchers who have an existing list of articles they have read in their field but are looking for related articles.

## Introducing DigDeeper

DigDeeper addresses this issue by recommending and ranking articles based on information extracted from a few existing research articles. It identifies what you should be reading next by analyzing your current set of research articles.
For demonstration, I will be using my research area: functional near-infrared spectroscopy (fNIRS).

# Methodology:

![DigDeeper](https://github.com/user-attachments/assets/3660fa3f-1389-4b24-847d-456bf5c28094)

In this project, I utilized Elsevier's API to extract full text and metadata, including abstracts, journal names, publication years, keywords, citations, and references. Additionally, journal quality metrics such as SNIP and SJR were considered. The system calculates text similarity by vectorizing the article contents, keywords, and abstracts. For a selected article or a folder of selected articles, the algorithm assigns scores to newer articles based on the weighted average of text similarity, shared citations, publication year, and journal quality.

A word cloud generated from the abstracts in my current folder is shown below:


![Wordcloud from Abstract](https://github.com/user-attachments/assets/c48fd159-c816-4c8d-9e7a-4e9c97806c06)

To evaluate the performance of our method, we also downloaded 50 articles from various fields, including fNIRS, fMRI, Psychology, and Geology. As expected, these article groups are ranked in descending order of similarity to my collection.

![image](https://github.com/user-attachments/assets/2b8cb8c0-1662-4a0e-9bb8-53ba7eb14730)

When asked to recommend articles, the algorithm ranks and identifies new articles as shown below:

| id   | doi                                    | title                                               | url                                                      | scores    |
|------|----------------------------------------|-----------------------------------------------------|----------------------------------------------------------|-----------|
| 833  | 10.1016/j.neuroimage.2012.03.049       | A brief review on the history of human functio...   | [Link](https://www.sciencedirect.com/science/article/...) | 3.317256  |
| 1080 | 10.1016/j.neuron.2014.05.001           | Discriminative and Affective Touch: Sensing an...    | [Link](https://www.sciencedirect.com/science/article/...) | 2.985293  |
| 1083 | 10.1016/j.neuron.2017.06.041           | Discovering Event Structure in Continuous Narr...    | [Link](https://www.sciencedirect.com/science/article/...) | 2.702325  |
| 1082 | 10.1016/j.neuron.2015.09.022           | Centrality of Social Interaction in Human Brai...    | [Link](https://www.sciencedirect.com/science/article/...) | 2.539782  |
| 1081 | 10.1016/j.neuron.2015.03.023           | Different Functional Neural Substrates for Goo...    | [Link](https://www.sciencedirect.com/science/article/...) | 2.421528  |

If we decide to add any recommended articles to our list, the algorithm is retrained on the newer articles to improve future recommendations.


# Summary
In this project, we developed an article recommendation system using Elsevier's API to extract comprehensive metadata and full-text information from scholarly articles. The system utilizes advanced text similarity algorithms to recommend new articles based on a user's existing collection. By incorporating journal quality metrics such as SNIP and SJR, and analyzing factors like publication year and shared citations, the algorithm ranks and identifies relevant articles. We demonstrated the system's effectiveness by analyzing articles from various fields, including fNIRS, fMRI, Psychology, and Geology. The algorithm continuously improves by retraining on newly added articles, ensuring that recommendations remain up-to-date and highly relevant to the user's research interests.

