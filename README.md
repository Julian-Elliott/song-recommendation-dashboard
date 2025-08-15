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
* Describe your dataset. Choose a dataset of reasonable size to avoid exceeding the repository's maximum size of 100Gb.


## Business Requirements
* Describe your business requirements


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
  - **Content-Based Similarity Assumptions:**  
    Do songs with similar audio features receive similar ratings/preferences?  
    *Tested using similarity metrics and correlation with user preferences.*

## Project Plan
* Outline the high-level steps taken for the analysis.
* How was the data managed throughout the collection, processing, analysis and interpretation steps?
* Why did you choose the research methodologies you used?

## The rationale to map the business requirements to the Data Visualisations
* List your business requirements and a rationale to map them to the Data Visualisations

## Analysis techniques used

* **Data Cleaning:**  
  Before analysis, we cleaned the dataset by removing duplicate tracks, handling missing values, and ensuring that all audio feature columns contained valid numerical data. We also standardised column names and filtered out any records with incomplete or inconsistent information. This step was essential to ensure the accuracy and reliability of our analysis and recommendations.

* **Feature Engineering:**  
  We created new features and transformed existing ones to improve the performance of our recommendation system. This included combining or modifying audio features, encoding categorical variables, and selecting the most relevant features for analysis. Feature engineering helped us better capture the characteristics of songs and user preferences.

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
### Heroku

* The App live link is: https://YOUR_APP_NAME.herokuapp.com/ 
* Set the runtime.txt Python version to a [Heroku-20](https://devcenter.heroku.com/articles/python-support#supported-runtimes) stack currently supported version.
* The project was deployed to Heroku using the following steps.

1. Log in to Heroku and create an App
2. From the Deploy tab, select GitHub as the deployment method.
3. Select your repository name and click Search. Once it is found, click Connect.
4. Select the branch you want to deploy, then click Deploy Branch.
5. The deployment process should happen smoothly if all deployment files are fully functional. Click now the button Open App on the top of the page to access your App.
6. If the slug size is too large then add large files not required for the app to the .slugignore file.


## Main Data Analysis Libraries
* Here you should list the libraries you used in the project and provide an example(s) of how you used these libraries.


## Credits 

* In this section, you need to reference where you got your content, media and extra help from. It is common practice to use code from other repositories and tutorials, however, it is important to be very specific about these sources to avoid plagiarism. 
* You can break the credits section up into Content and Media, depending on what you have included in your project. 

### Content 

- The text for the Home page was taken from Wikipedia Article A
- Instructions on how to implement form validation on the Sign-Up page was taken from [Specific YouTube Tutorial](https://www.youtube.com/)
- The icons in the footer were taken from [Font Awesome](https://fontawesome.com/)

### Media

- The photos used on the home and sign-up page are from This Open-Source site
- The images used for the gallery page were taken from this other open-source site



## Acknowledgements (optional)
* Thank the people who provided support through this project.
