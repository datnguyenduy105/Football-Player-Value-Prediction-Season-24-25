# Football Player Value Prediction Season 24/25

### **Project Overview**

This project aims to predict football player market values based on their performance statistics. It leverages data from two reputable sources: Transfermarkt (market values) and FBRef (detailed player statistics). The project combines web scraping, data cleaning, preprocessing, unsupervised learning (clustering), and supervised learning (predictive modeling) to achieve its objective. The analysis focuses on five major European leagues: Premier League, La Liga, Serie A, Bundesliga, and Ligue 1.
---
### **Dataset**

The project uses two primary datasets:

1.  **Transfermarkt Data:** Scraped data containing player names, teams, and market values for the five specified leagues. This data is initially collected in separate CSV files per league and then consolidated into a single file (top5_league_market_values.csv) after cleaning.
2.  **FBRef Data:** Ten CSV files containing a wide range of player statistics from FBRef, covering various aspects of player performance (e.g., passing, shooting, defense, possession). These datasets are cleaned, preprocessed, and merged into a single DataFrame for further analysis.
---
### **Methodology**

The project follows a structured approach:

1.  **Data Acquisition** Web scraping is employed to collect player market values from Transfermarkt.
2.  **Data Cleaning** The scraped data undergoes cleaning to handle missing values, inconsistencies, and non-uniform data formats. Currency symbols are removed, and market values are converted to numerical representations. Duplicate player entries are handled appropriately, based on maximum minutes played for the specific player in different teams.
3.  **Data Preprocessing and Integration:** The cleaned FBRef and Transfermarkt datasets are merged based on player name and team. Feature selection is performed to select the most relevant attributes for analysis and modeling, excluding goalkeepers and players with fewer than 90 minutes of play time.
4.  **Exploratory Data Analysis (EDA):** EDA is conducted using techniques such as correlation analysis and distribution plots (histograms, box plots) to explore relationships between player statistics and market values and to identify potential outliers.
5.  **Unsupervised Learning (Clustering):** KMeans clustering is performed on the combined dataset to group players with similar performance profiles and market values. This process identified distinct player archetypes within each position. For example:
    *   Defenders were clustered into groups such as "Defensive Center-Back," "Attacking Full-Back", "Aerial Duel Specialist," and a cluster potentially representing outliers or incomplete data.
    *   Midfielders were grouped into clusters like "Deep-Lying Playmaker," "Defensive-minded Midfielder," "Creative Midfielder," "Balanced Midfielder," and "Possession Retriever."
    *   Forwards were clustered into "Target Man," "Hard-Working Forward," "Inside Forward," and "Dribbling Winger" types.
6.  **Supervised Learning (Predictive Modeling):** Various regression models (e.g., linear regression, SVR, random forest, gradient boosting...) are trained to predict player market values using the player statistics as predictors. Model performance is evaluated using metrics like R-squared, Mean Squared Error (MSE), and Mean Absolute Error (MAE). The best-performing Gradient Boosting model achieved a Test MAE of 0.55 and Validation R²: 0.61. The results help to identify the most influential factors in determining player market value.
---
### **Skills Demonstrated:**

*   Web scraping (using urllib and BeautifulSoup)
*   Data cleaning and preprocessing (using pandas, regular expressions, and potentially imputation techniques)
*   Data analysis and visualization (using pandas, matplotlib, and seaborn)
*   Unsupervised machine learning (KMeans clustering)
*   Supervised machine learning (regression modeling with scikit-learn)
---
### **Business/Real-World Application:**

This model can be a valuable tool for football clubs to identify undervalued players in the transfer market based on their statistical performance compared to their current market value. Furthermore, it could assist in projecting the future market value increase of promising young players based on their developing skillset.
---
### **Considerations**

The model's accuracy and reliability depend heavily on the quality and completeness of the input data. Potential biases within the datasets (e.g., underrepresentation of certain player positions or nationalities) could lead to biased predictions, a limitation requiring careful attention in future work.
---
### **Limitations and Future Enhancements**

*   Exploring advanced regression techniques for improved predictive accuracy and interpretability.
*   Incorporating additional features, such as injury history, playing style, contract details, and qualitative factors influencing value.
*   Expanding the analysis to include more leagues or competitions.
*   Investigating and mitigating potential biases within the data.
---
### **Conclusion**

This project offers a robust framework for predicting football player market values. The integration of web scraping, data cleaning, and machine learning techniques provides a valuable analytical tool with practical applications for football clubs and analysts.
