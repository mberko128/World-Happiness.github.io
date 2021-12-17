-   [Introduction](#introduction)
-   [Data Organization](#data-organization)
-   [Exploratory Data Analysis](#exploratory-data-analysis)
    -   [Summary Statistics](#summary-statistics)
    -   [Correlation Heatmap](#top-10-states-by-number-of-accidents)
    -   [Scatterplots](#scatterplots)
-   [Conclusions](#conclusions)
    -   [Main Observations](#main-observations)
    -   [Future Directions](#future-directions)
-   [Run Notebook in Google Colab](#run-notebook-in-google-colab)
-   [Youtube Video Link](#youtube-video-link)
-   [Inquiries](#inquiries)
-   [Data Sources](#data-sources)
-   [Acknowledgments](#acknowledgments)


# Introduction
The COVID-19 pandemic has brought to light just how important happiness and mental health is in our lives. During times of lockdown, many individuals found themselves struggling with mental health issues and craving the things and activities that bring us most joy. In other words, the pandemic highlighted just how important being happy is for our mental health and forced us to reflect on the specific elements of our lives that bring us happiness.

Everyone wants to live the happiest life they can. For some, social support may be the most important aspect of being happy. For others, happiness may stem from economic success, helping others, or having the freedom and opportunity to do what they wish. Through the data science process, our group will try and decipher what elements foster happiness on a global scale. In other words, we will try to answer the following question: **What are the most influential factors in one’s life to being happy?**

Our analysis has the potential to provide valuable and actionable insights for policymakers and law-makers, whose ultimate goal is to create and implement policies that will best benefit society. In the unprecedented times we have been living in with the pandemic, being happy and having good mental health has never been so important. Our analysis can hopefully shed some light as to whether social networks, financial success, or some other factor may impact happiness the most, which policymakers can use to inspire practices that are most likely to foster happiness among society at large.

# Data Organization
In order to gain insight into what factors most influence one’s happiness, we will use a dataset provided by the United Nations entitled World Happiness. The UN reports world happiness data on a yearly basis. This is the most recent dataset on the subject. 

The UN uses data collected from the Gallup World Poll, which surveys individuals on main life evaluation questions. The Gallup World Poll  is conducted yearly in at least 153 countries with a random sample of at least 1000 respondents in each country. Participants of the survey were asked how a number of different factors, such as social support and freedom to make life choices, impacted the overall happiness in their lives from 0 to 10, with 10 being the best possible life and 0 being the worst. They are also asked to rate their overall happiness level in their lives, on this same 0 to 10 scale. Other varriables in the dataset were binary survey questions, so respondents answered with either a 0 or 1. The values for these variables are averaged for each country and year. The data collected is based entirely on the survey scores, using the Gallup weights to make the estimates representative. 

After our data manipulation and subsetting processes, we ended up with the following data frame:

Attribute | Data Type | Description |
--- | --- | --- 
Life Ladder | Ratio | Describes respondents overall life happiness on a scale of 0-10
Social Support | Ratio | Describes the national average of the binary responses (either 0 or 1) to the question <br> “If you were in trouble, do you have relatives or friends you can count on to help you whenever you need them, or not?”
Healthy Life Expextancy at Birth | Ratio | The time series of healthy life expectancy at birth constructed based on data from the World Health Organization (WHO) <br> Global Health Observatory data repository, with data available for 2005, 2010, 2015, and 2016. 
Freedom to Make Life Choices | Ratio | National average of binary responses to the GWP question “Are you satisfied or dissatisfied with your freedom to choose <br> what you do with your life?”
Generosity | Ratio | Describes the residual of regressing the national average of GWP responses to the question “Have you donated money to a <br> charity in the past month?” on GDP per capita.
Perceptions of Corruption | Ratio | Describes the average of binary answers to two GWP questions: “Is corruption widespread throughout the government or not?” <br> and “Is corruption widespread within businesses or not?” Where data for government corruption are missing, the perception of <br> business corruption is used as the overall corruption-perception measure.
Positive affect | Ratio | Desrcibes the average of previous-day affect measures for happiness, laughter, and enjoyment for years 2008 to 2012, and some in 2013
Negative affect | Ratio | Decribes the average of previous-day affect measures for worry, sadness, and anger for all years.

# Exploratory Data Analysis
