# YouTube Performance Prediction – Semiannual Dataset (2017)

This repository contains a machine learning project developed during my internship at **Corizo Edutech Pvt. Ltd.** The goal of the project was to predict YouTube video performance metrics such as views, likes, and comments using supervised learning techniques.

## Project Background

The dataset used in this project was provided by the company and was originally scraped and cleaned by their internal team. It contains **semiannual data** spanning from **May 2017 to November 2017**, representing a snapshot of trending videos over that period. The dataset is not publicly available and was used for internal training and evaluation purposes.

## Dataset Description

The dataset includes approximately **16,000+ video entries** with the following attributes:

- `title`: Title of the YouTube video  
- `channel_title`: Name of the channel  
- `category_id`: Numeric ID representing the category  
- `publish_time`: ISO timestamp when the video was published  
- `views`: Total number of views  
- `likes`: Number of likes  
- `dislikes`: Number of dislikes  
- `comment_count`: Total number of comments  
- `comments_disabled`, `ratings_disabled`, `video_error_or_removed`: Boolean indicators  
- `tags`, `description`, and other metadata

The `publish_time` field was transformed to extract `publish_date` and weekday information, though some columns were dropped during preprocessing to focus on numeric modeling.

## Objective

The objective was to design and evaluate regression models to predict:

- View count  
- Like count  
- Comment count  

These are treated as separate supervised regression problems using the same base dataset.

## Workflow

The complete pipeline follows these stages:

1. **Data Cleaning & Preprocessing**  
   - Dropping non-numeric and irrelevant columns  
   - Handling missing values and invalid entries  
   - Converting timestamps into usable date components  

2. **Exploratory Data Analysis (EDA)**  
   - Correlation matrix  
   - Outlier detection and visualizations  
   - Feature-target analysis  

3. **Feature Engineering**  
   - Dropped low-correlation features  
   - Focused on numeric attributes influencing engagement  

4. **Model Building**  
   Separate models were built for each target variable using:
   - Linear Regression  
   - Random Forest Regressor (with hyperparameter tuning via GridSearchCV)  
   - Support Vector Machine (SVR)  

5. **Model Evaluation**  
   - Train-test split (80:20 ratio)  
   - Metrics: R² score, Mean Squared Error (MSE), and visual comparison  
   - Feature importance interpretation (for Random Forest)

## Key Outcomes

- Random Forest consistently outperformed Linear Regression and SVM across all three prediction tasks.  
- Likes and Views showed strong correlation, enabling better prediction performance than comment count.  
- GridSearchCV tuning improved SVM and RF results, particularly in predicting likes.

## Tools & Technologies Used

- Python 3.8+  
- Jupyter Notebook  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- Scikit-learn (LinearRegression, RandomForestRegressor, SVR, GridSearchCV)

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

## Acknowledgements

Special thanks to **Corizo Edutech Pvt. Ltd.** for providing the dataset and internship opportunity where this project was conceptualized and executed as part of their Data Analytics Internship Program.
