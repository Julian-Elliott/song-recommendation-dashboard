# ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)
# Spotify Tracks Dataset Analysis
## Overview

The objective of this project is to predict song recommendations using features within the [Spotify Tracks Dataset](https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset), such as danceability, energy, loudness, instrumentalness, and liveness. We employ a nearest neighbour machine learning approach to suggest songs that are similar in musical characteristics, providing users with tailored recommendations based on their preferences.

Our dataset contains 89,741 unique tracks, each with detailed information including:
- Track name, artist, and album
- Popularity score
- Release date
- Audio features (danceability, energy, loudness, speechiness, acousticness, instrumentalness, liveness, valence, tempo)
- Genre and playlist information

By leveraging these features and machine learning techniques, this project aims to deliver accurate and relevant song recommendations, supporting data-driven decision making for music discovery and personalisation.


## Dataset Content

The Spotify Tracks Dataset contains the following key columns for each track:

- **track_id**: Unique identifier for each track
- **track_name**: Name of the song
- **artists**: Name(s) of the artist(s)
- **album_name**: Name of the album
- **popularity**: Popularity score assigned by Spotify
- **release_date**: Date the track was released
- **danceability**: How suitable a track is for dancing (0.0–1.0)
- **energy**: Intensity and activity of the track (0.0–1.0)
- **loudness**: Overall loudness in decibels
- **speechiness**: Presence of spoken words (0.0–1.0)
- **acousticness**: Confidence measure of whether the track is acoustic (0.0–1.0)
- **instrumentalness**: Predicts if a track contains no vocals (0.0–1.0)
- **liveness**: Presence of a live audience (0.0–1.0)
- **valence**: Musical positiveness (0.0–1.0)
- **tempo**: Estimated tempo in beats per minute (BPM)
- **duration_ms**: Duration of the track in milliseconds
- **genre**: Genre(s) associated with the track
- **playlist_name**: Name of the playlist the track appears in (if available)

This rich set of features enables detailed analysis of musical characteristics and user preferences for recommendation purposes.

## Business Requirements

The primary business requirements for this project are:

1. **Personalised Song Recommendations:**  
  Provide users with accurate and relevant song recommendations based on their musical preferences and listening history, enhancing user engagement and satisfaction.

2. **Support for Music Discovery:**  
  Enable users to discover new tracks and artists that match their tastes, encouraging exploration beyond their usual listening habits.

3. **Data-Driven Insights:**  
  Offer insights into the factors that influence song popularity and user preferences, supporting decision-making for playlist curation and marketing strategies.

4. **Scalability and Efficiency:**  
  Ensure that the recommendation system can efficiently handle large volumes of tracks and user data, allowing for future growth and integration with other music platforms.

5. **Transparency and Interpretability:**  
  Provide clear explanations of how recommendations are generated, helping users and stakeholders understand the reasoning behind suggested tracks.


## Key Findings from Data Analysis

Our comprehensive exploratory data analysis revealed several critical insights that directly inform our recommendation system design:

### **Data Quality Excellence**
- **Perfect Completeness:** 100% data completeness across all 89,741 tracks with zero missing values
- **High Data Integrity:** Minimal duplicate records ensuring clean foundation for recommendations
- **Comprehensive Coverage:** 11+ detailed audio features providing rich characteristic profiles

### **Audio Feature Insights**
Based on our analysis visualisations:

**Distribution Patterns** (`numerical_features_distribution.png`):
- Several features show non-normal distributions requiring preprocessing
- Tempo and popularity features exhibit significant outliers
- Valence and danceability show more uniform distributions suitable for similarity calculations

**Feature Correlations** (`audio_features_correlation_matrix.png`):
- **Strong positive correlation** between energy and loudness (r > 0.5)
- **Moderate correlation** between valence and danceability
- **Independence** of acousticness and energy features, providing diverse recommendation dimensions

**Feature Quality** (`audio_features_box_plots.png`):
- Systematic outlier detection across all audio characteristics
- Well-defined quartile ranges for most features
- Clear statistical boundaries for similarity thresholds

### **Genre Distribution Analysis**
Our complete treemap visualisation (`genre_distribution_complete_treemap.png`) reveals:
- **Excellent Genre Balance:** Near-perfect distribution across all music genres
- **Comprehensive Coverage:** All genres represented with unique visual identification
- **Single Exception:** K-pop shows higher representation (999 tracks) but doesn't compromise overall balance
- **Recommendation Diversity:** Strong foundation for cross-genre music discovery

### **Statistical Validation**
- **Skewness Analysis:** Identified features requiring transformation for optimal model performance
- **Bias Assessment:** Low Gini coefficient indicates equitable genre representation
- **Preprocessing Validation:** Standard scaling confirmed as optimal approach for computational efficiency

### **Implications for Recommendation System**
These findings directly support our business requirements:
1. **Robust Data Foundation:** High-quality, complete dataset enables reliable recommendations
2. **Feature Diversity:** Multiple uncorrelated audio dimensions provide rich similarity calculations
3. **Genre Fairness:** Balanced representation ensures diverse music discovery
4. **Scalable Architecture:** Clean data structure supports efficient similarity computations

## Hypothesis and how to validate?
* We formulated and tested several hypotheses to guide our recommendation approach:
  - **Genre-Based Audio Feature Differences:**  
    Do audio features differ significantly between genres?  
    *Tested using ANOVA to compare feature distributions across genres.*
  - **Popularity vs. Audio Features:**  
    Do popular songs have different audio characteristics than less popular songs?  
    *Tested using t-tests and effect size calculations.*
  - **Audio Feature Correlations:**  
    Are there significant correlations between audio features?  
    *Tested using correlation matrices and significance testing.*

## Why we did our Hypotheses

We developed and tested several hypotheses to ensure our recommendation system is based on sound assumptions and real-world patterns. By validating these hypotheses, we aimed to:
- Understand how audio features differ across genres and popularity levels
- Identify which features are most important for recommendations
- Ensure that our model reflects actual user preferences and behaviours
- Provide a transparent and data-driven foundation for our recommendation approach

This process helps us build a more effective and trustworthy system for music discovery and personalisation.

## Project Plan

The high-level steps taken for the analysis are as follows:

1. **Data Cleaning:** Remove duplicates, handle missing values, and ensure all audio feature columns contain valid data.
2. **Feature Engineering:** Create new features and transform existing ones to better capture song characteristics and user preferences.
3. **Exploratory Data Analysis:** Visualise and summarise the dataset to understand distributions and relationships.
4. **Hypothesis Testing:** Formulate and test hypotheses to validate assumptions about music preferences and recommendation strategies.
5. **Model Development:** Build and evaluate a nearest neighbour recommendation model.
6. **Dashboarding:** Present the results and insights through an interactive dashboard for stakeholders and users.

## The rationale to map the business requirements to the Data Visualisations

### 1. Personalised Song Recommendations
**Data Visualisation:** Audio Features Correlation Matrix (`audio_features_correlation_matrix.png`)
- **Rationale:** Understanding correlations between audio features helps identify which characteristics cluster together, enabling more accurate similarity-based recommendations.
- **Key Finding:** Strong correlations identified between energy-loudness and valence-danceability, informing our feature weighting strategy.

### 2. Support for Music Discovery  
**Data Visualisation:** Complete Genre Distribution Treemap (`genre_distribution_complete_treemap.png`)
- **Rationale:** Visualising genre distribution ensures our recommendation system can suggest diverse music across all available genres, not just popular ones.
- **Key Finding:** Nearly perfect genre balance discovered (except K-pop with 999 tracks), supporting effective cross-genre recommendations.

### 3. Data-Driven Insights
**Data Visualisations:** 
- Numerical Features Distribution (`numerical_features_distribution.png`)
- Audio Features Box Plots (`audio_features_box_plots.png`)
- **Rationale:** Distribution analysis reveals data quality, skewness patterns, and outliers that impact recommendation algorithms.
- **Key Findings:** Several highly skewed features identified requiring log transformation; outlier patterns detected in tempo and popularity metrics.

### 4. Scalability and Efficiency
**Data Visualisation:** Standardisation Comparison (`standardisation_comparison.png`)
- **Rationale:** Comparing preprocessing techniques ensures optimal data preparation for efficient similarity calculations at scale.
- **Key Finding:** Standard scaling chosen for computational efficiency while maintaining recommendation accuracy.

### 5. Transparency and Interpretability
**Data Visualisation:** Audio Features Distribution (`audio_features_distribution.png`)
- **Rationale:** Clear visualisation of feature ranges and distributions helps explain to users why certain songs are recommended.
- **Key Finding:** Audio features show interpretable patterns that can be communicated to end users for recommendation explanations.

## Analysis techniques used

* **Data Cleaning:**  
  Before analysis, we cleaned the dataset by removing duplicate tracks, handling missing values, and ensuring that all audio feature columns contained valid numerical data. We also standardised column names and filtered out any records with incomplete or inconsistent information. This step was essential to ensure the accuracy and reliability of our analysis and recommendations.
  
  **Key Results:** Achieved 100% data completeness with zero missing values across 89,741 tracks, as visualised in our comprehensive data quality analysis.

* **Exploratory Data Analysis:**  
  We conducted extensive visualisation and statistical analysis to understand our dataset characteristics:
  
  - **Distribution Analysis** (`numerical_features_distribution.png`): Revealed skewness patterns across audio features, with several features requiring transformation for optimal model performance.
  - **Correlation Analysis** (`audio_features_correlation_matrix.png`): Identified significant correlations between energy-loudness (r > 0.5) and moderate correlations between valence-danceability, informing our feature selection strategy.
  - **Genre Distribution** (`genre_distribution_complete_treemap.png`): Discovered near-perfect genre balance across all categories, with unique colour coding for each of the genres represented, ensuring comprehensive music discovery capabilities.
  - **Outlier Detection** (`audio_features_box_plots.png`): Systematically identified outliers in tempo, popularity, and duration features, with detailed quartile analysis for each audio characteristic.

* **Feature Engineering:**  
  We created new features and transformed existing ones to improve the performance of our recommendation system. This included combining or modifying audio features, encoding categorical variables, and selecting the most relevant features for analysis. Feature engineering helped us better capture the characteristics of songs and user preferences.
  
  **Preprocessing Results** (`standardisation_comparison.png`): Implemented standard scaling for computational efficiency while maintaining recommendation accuracy across all audio features.

* **Statistical Analysis:**
  - **Skewness Assessment:** Identified highly skewed features (|skew| > 2) requiring log transformation
  - **Correlation Testing:** Validated feature relationships using significance testing
  - **Distribution Quality:** Assessed normality and identified optimal preprocessing strategies
  - **Bias Detection:** Implemented Gini coefficient analysis for genre inequality measurement

* The method we use to prepare the data (called "standard scaling") does not handle unusual values or imbalances in the data. This means that songs that are very different from most others could affect our results. For this project, we decided not to address this issue, as it is outside the scope of our first version. However, looking into this in the future could help us make even more accurate music recommendations.



## Ethical considerations

- The Spotify Tracks Dataset may include explicit content or tracks by controversial/cancelled artists. Care must be taken to avoid recommending such songs to minors or sensitive users. Implementing content filters or explicit content warnings is strongly advised.
- Data privacy is not a direct concern as the dataset contains no personal user information, but ethical use of the data and respect for copyright and licensing should be maintained.
- Bias may exist in the dataset, such as overrepresentation of certain genres, artists, or regions, which could affect the fairness of recommendations. Regularly review and, if possible, mitigate these biases in your analysis and recommendation algorithms.
- Consider the societal impact of music recommendations, especially regarding exposure to explicit or potentially harmful content.

> **Note:**
> 
> The Spotify Tracks Dataset may contain explicit songs or tracks by artists who have been cancelled or are considered controversial. Care should be taken when recommending such songs, especially as minors or sensitive users could use this analysis or any resulting dashboard. It is important to consider filtering or flagging explicit or potentially inappropriate content in any recommendation system built from this dataset.

## Dashboard Design
* List all dashboard pages and their content, either blocks of information or widgets, like buttons, checkboxes, images, or any other item that your dashboard library supports.
* Later, during the project development, you may revisit your dashboard plan to update a given feature (for example, at the beginning of the project you were confident you would use a given plot to display an insight but subsequently you used another plot type).
* How were data insights communicated to technical and non-technical audiences?
* Explain how the dashboard was designed to communicate complex data insights to different audiences. 

## Unfixed Bugs
* Please mention unfixed bugs and why they were not fixed. This section should include shortcomings of the frameworks or technologies used. Although time can be a significant variable to consider, paucity of time and difficulty understanding implementation are not valid reasons to leave bugs unfixed.
* Did you recognise gaps in your knowledge, and how did you address them?
* If applicable, include evidence of feedback received (from peers or instructors) and how it improved your approach or understanding.

## Development Roadmap
* What challenges did you face, and what strategies were used to overcome these challenges?
* What new skills or tools do you plan to learn next based on your project experience? 

## Deployment
### Tableau Public

* The live dashboard is available at: https://public.tableau.com/app/profile/julian.elliott/viz/song-recommendation-dashboard/SongSelector
* The project was deployed to Tableau Public using the following steps:

1. **Data Preparation:** Export the processed datasets from our Python analysis pipeline as CSV files for Tableau consumption
2. **Dashboard Development:** Create interactive visualisations in Tableau Desktop using the recommendation data
3. **Tableau Public Upload:** 
   - Log in to Tableau Public
   - Upload the Tableau workbook (.twb) file containing all visualisations and data connections
   - Configure public access and sharing settings
4. **Interactive Features:** The dashboard includes:
   - Song selector interface for exploring recommendations
   - Interactive filters for genre, popularity, and audio features
   - Dynamic visualisations showing recommendation relationships
   - Album artwork integration via Spotify URLs
5. **Data Updates:** The dashboard can be refreshed by re-uploading updated CSV files from our recommendation pipeline


## Main Data Analysis Libraries

The following libraries were essential for our comprehensive analysis and visualisation generation:

### **Core Data Analysis:**
* **pandas (2.3.1):** Used for data manipulation, cleaning, and statistical analysis of our 89,741 track dataset
  ```python
  df = pd.read_csv("spotify_tracks.csv")
  genre_counts = df['genre'].value_counts()
  ```

* **numpy (2.3.2):** Provided numerical computing capabilities for statistical calculations and array operations
  ```python
  # Skewness calculations and correlation analysis
  skew_val = stats.skew(df[col].dropna())
  ```

### **Statistical Analysis:**
* **scipy (1.16.1):** Used for advanced statistical testing and skewness analysis
  ```python
  from scipy import stats
  # Distribution analysis for each numerical feature
  ```

### **Visualisation Libraries:**
* **matplotlib (3.10.5):** Created foundational plots and figure management for all our analysis charts
  ```python
  # Generated: numerical_features_distribution.png, audio_features_box_plots.png
  plt.figure(figsize=(24, 16))
  ```

* **seaborn (0.13.2):** Produced statistical visualisations including correlation heatmaps
  ```python
  # Generated: audio_features_correlation_matrix.png
  sns.heatmap(corr_matrix, annot=True, cmap='RdBu_r')
  ```

* **squarify (0.4.4):** Created our comprehensive genre distribution treemap with unique colours for each genre
  ```python
  # Generated: genre_distribution_complete_treemap.png
  squarify.plot(sizes=genre_counts.values, labels=labels, color=colors)
  ```

### **Generated Visualisations:**
Our analysis produced six key visualisation files saved in `/results/`:
1. `numerical_features_distribution.png` - Distribution analysis of all audio features
2. `audio_features_correlation_matrix.png` - Feature correlation heatmap
3. `genre_distribution_complete_treemap.png` - Comprehensive genre representation
4. `audio_features_box_plots.png` - Outlier detection and quartile analysis
5. `audio_features_distribution.png` - Individual feature distribution patterns
6. `standardisation_comparison.png` - Preprocessing technique validation

Each visualisation directly supports our recommendation system development and validates key assumptions about the dataset characteristics.


## Credits 

- GitHub Copilot: Supported with code guidance, code errors, data exploration ideas, markdown writing, and troubleshooting

- Kaggle: For providing the music streaming and recommendation system dataset

- Code Institute: For the project structure and teamwork framework

- Team Members: Julian, Nassra, Sumaya 

### Media

- The background image on our Tableau dashboard was generated with the multimodal ChatGPT-5 image generator.
- The album artwork present on our dashboard uses Spotify's album artwork hosted at their URLs, which is free to use with attribution of their logo, which is present in our README and presentation.