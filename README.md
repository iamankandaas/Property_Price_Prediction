<!DOCTYPE html>
<html>
<head>
    <title>Property Price Prediction Project</title>
</head>
<body>
    <h1>Property Price Prediction Project</h1>

    <h2>Overview</h2>
    <p>
        This project focuses on predicting median house values in California districts using district-level features. 
        It employs <strong>Simple Linear Regression</strong> and <strong>Multiple Linear Regression</strong> to identify key factors influencing housing prices and to develop predictive models. 
        The project also demonstrates various data preprocessing and feature engineering techniques to improve model performance.
    </p>

    <h2>Project Workflow</h2>

    <h3>1. Data Preprocessing</h3>
    <ul>
        <li>Handled missing values in the <code>total_bedrooms</code> column by imputing the median.</li>
        <li>Created new composite features to reduce multicollinearity:
            <ul>
                <li><code>rooms_per_household</code> = <code>total_rooms</code> / <code>households</code></li>
                <li><code>bedrooms_per_room</code> = <code>total_bedrooms</code> / <code>total_rooms</code></li>
                <li><code>population_per_household</code> = <code>population</code> / <code>households</code></li>
            </ul>
        </li>
        <li>Dropped highly correlated features: <code>total_rooms</code>, <code>total_bedrooms</code>, <code>population</code>, and <code>households</code>.</li>
        <li>Encoded the categorical feature <code>ocean_proximity</code> using one-hot encoding.</li>
        <li>Normalized numerical features using MinMaxScaler for consistent input ranges.</li>
        <li>Added polynomial features (squared and cubed terms) for <code>median_income</code>.</li>
        <li>Introduced interaction terms, e.g., <code>median_income * housing_median_age</code>.</li>
        <li>Applied log transformations to stabilize variance in skewed features.</li>
    </ul>

    <h3>2. Modeling</h3>
    <h4>Simple Linear Regression</h4>
    <ul>
        <li><strong>Predictor:</strong> <code>median_income</code></li>
        <li><strong>Target:</strong> <code>median_house_value</code></li>
        <li><strong>RMSE:</strong> 0.1736, <strong>R²:</strong> 0.4589</li>
    </ul>

    <h4>Multiple Linear Regression</h4>
    <ul>
        <li><strong>Predictors:</strong> All features after preprocessing.</li>
        <li><strong>Target:</strong> <code>median_house_value</code></li>
        <li><strong>RMSE:</strong> 0.01697, <strong>R²:</strong> 0.9948</li>
    </ul>

    <h2>Technologies Used</h2>
    <ul>
        <li><strong>Programming Language:</strong> Python</li>
        <li><strong>Libraries:</strong>
            <ul>
                <li>Data Analysis: <code>pandas</code>, <code>numpy</code></li>
                <li>Visualization: <code>seaborn</code>, <code>matplotlib</code></li>
                <li>Machine Learning: <code>scikit-learn</code></li>
                <li>Preprocessing: <code>MinMaxScaler</code></li>
            </ul>
        </li>
    </ul>

    <h2>How to Run</h2>
    <ol>
        <li>Clone the repository:
            <pre><code>git clone https://github.com/your-username/property-price-prediction.git</code></pre>
        </li>
        <li>Install dependencies:
            <pre><code>pip install -r requirements.txt</code></pre>
        </li>
        <li>Run the main script:
            <pre><code>python main.py</code></pre>
        </li>
    </ol>

    <h2>Results</h2>
    <ul>
        <li><strong>Simple Linear Regression:</strong> Demonstrated limited predictive power with an R² score of 0.4589.</li>
        <li><strong>Multiple Linear Regression:</strong> Significantly improved performance with an R² score of 0.9948 after refinements.</li>
    </ul>

    <h2>Project Files</h2>
    <ul>
        <li><strong><code>main.py</code>:</strong> The main Python script to run the project.</li>
        <li><strong><code>data/</code>:</strong> Folder containing the dataset.</li>
        <li><strong><code>notebooks/</code>:</strong> Jupyter Notebooks with detailed steps and visualizations.</li>
        <li><strong><code>README.md</code>:</strong> Project documentation.</li>
        <li><strong><code>requirements.txt</code>:</strong> List of required Python libraries.</li>
    </ul>

    <h2>Future Work</h2>
    <ul>
        <li>Validate the model on unseen data to assess generalization.</li>
        <li>Experiment with advanced regression techniques, such as Ridge or Lasso Regression.</li>
        <li>Explore non-linear models like Decision Trees or Random Forest.</li>
    </ul>

    <h2>Acknowledgements</h2>
    <p>
        This project is inspired by Internshala Trainings and the California Housing dataset.
    </p>
</body>
</html>
