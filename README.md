# Body Fat Estimation Using Machine Learning Algorithms

## Project Overview

In this project, the goal is to develop a machine learning model to estimate body fat percentage based on anthropometric measurements. Body fat estimation plays a crucial role in health assessment and fitness evaluation, making it a significant application in health analytics.

## Project Phases

1. **Data Collection and Description:**
   - [Body Fat Prediction Data Set](https://www.kaggle.com/datasets/fedesoriano/body-fat-prediction-dataset)  (Kaggle)

      The dataset contains anthropometric measurements including weight, height, neck circumference, chest circumference, abdomen circumference, hip circumference, thigh circumference, knee circumference, ankle circumference, biceps circumference, forearm circumference, and wrist circumference. In addition, it           includes actual body fat percentage measured using reliable methods. All measurements are numeric. The data set includes 252 instance and does not have any missing values. The data source is a structured CSV file. 
     
      ![Circumference Measurements](https://github.com/DesireeEDU/44688-Data-Analytics-Capstone-Project-Desiree-Thompson/blob/main/circumference%20_measurements.png)

2. **Data Cleaning and Preparation:**
   
   - The dataset does not include any missing values and or outliers that would require further handling.
   
   - In preparation for for further analysis, three (3) additional features have been added:
      - BMI
      - BMI Body Fat
      - Navy Baody Fat

3. **Exploratory Data Analysis (EDA):**
   - Conduct EDA to understand the distribution of variables, relationships between features, and identify patterns in the data. Utilize visualizations and statistical summaries to gain insights.

4. **Machine Learning Modeling:**
   - Implement machine learning algorithms such as linear regression, decision trees, random forests, or support vector machines (SVMs) to build predictive models for estimating body fat percentage. Evaluate model performance using metrics like Mean Absolute Error (MAE) or Root Mean Squared Error (RMSE).

5. **Advanced Analysis (Module 5 Requirement):**
   - Showcase advanced skills by potentially exploring more sophisticated techniques such as ensemble methods, neural networks, or feature engineering to enhance model accuracy in predicting body fat percentage.

6. **Presentation of Results and Insights:**
   - Create a professional report using LaTeX detailing project objectives, data sources, cleaning methods, modeling approaches, and results. Include correctly-formatted code blocks to demonstrate technical proficiency.

7. **GitHub Repository:**
   - Maintain an active GitHub repository containing all code, data files, notebooks, and documentation related to the project. Ensure clear organization and documentation for reproducibility and review.

## Deliverables

**Overleaf/LaTex Report: [Body Fat Estimation Using ML Algorithms](https://www.overleaf.com/read/zbrdqhmnqgvt#574be8)**
   - Detailed report showcasing professional communication and technical skills.
     
**GitHub Repository: [44688 Data Analytics Capstone Project](https://github.com/DesireeEDU/44688-Data-Analytics-Capstone-Project-Desiree-Thompson)**
   - Well-structured GitHub repository with code, data files, notebooks, and documentation, including a clickable link in the report for easy access.

## Usage

**File Structure:**
- `.gitignore`: Specifies which files are to be ignored during a commit. 
- `requirements.txt`: File listing the dependencies required by the project.
- `data_analytics_capstone_notebook.ipynb`: Includes data cleaning, exploratory data analysis, and model implementation.
- `circumference_measurements.png`: Shows the features that relate to circumference measurements.
- `bodyfat.csv`: Original data set
- `updated_bodyfat.csv`: Modified data set

**Project Setup and Installation:**
1. Create a virtual environment
   ```
   python3 -m venv ds-venv
   ```

2. Activate the environment
     - On Windows:
      ```
      ds-venv\Scripts\Activate
      ```
     - On macOS and Linux
      ```
      source env/bin/activate
      ```
   
3. Install the 
   ```
   pip install -r requirements.txt
   ```

6. Run the Program:
   - Open the Jupyter Notebook
   ```
   jupyter lab
   ```
   - Navigate to 'data_analytics_capstone_notebook.ipynb' and run the cells to execute the analysis

## Implementation

**Feature Selection**

 Upon review of the features that were strongly correlated it was deterined that the following featues have the strongest correlation and potentially predictive ability. 
  - Abdomen
  - Biceps
  - Hip
  - Neck
  - Thigh

This is reflected in the correlation coefficients plot

![Correlation Coefficients](https://github.com/DesireeEDU/44688-Data-Analytics-Capstone-Project-Desiree-Thompson/blob/main/Correlation%20Matrix.png)

**Model Selection**

Employed multiple regression techniques that include:
 - Linear Regression
 - Polynomial Regression
 - Elastic Net
 - Pipelined Linear Regression

**Training and Testing**

The dataset was split into a training set that consist of 80% and a test set of
20%. Each model was trained on the same training and test dataset. 

The following reflects the code used in training and testing the Linear Regression Model with features Abdomen, Biceps, Hip, Neck and Thigh:

![Sample Linear Regression Code](https://github.com/DesireeEDU/44688-Data-Analytics-Capstone-Project-Desiree-Thompson/blob/main/Sample%20Linear%20Regression%20Code.png)

**Results**

Results summary for the regression model testing to predict body fat:
<table>
  <tr>
    <th style="border-bottom: 2px solid black;">Model</th>
    <th style="border-bottom: 2px solid black;">Training Features</th>
    <th style="border-bottom: 2px solid black;">Train-RMSE</th>
    <th style="border-bottom: 2px solid black;">Train-R2</th>
    <th style="border-bottom: 2px solid black;">Test-RMSE</th>
    <th style="border-bottom: 2px solid black;">Test-R2</th>
  </tr>
  <tr>
    <td>Linear Regression</td>
    <td>Abdomen</td>
    <td>4.80</td>
    <td>67.07</td>
    <td>5.12</td>
    <td>61.76</td>
  </tr>
  <tr>
    <td>Linear Regression</td>
    <td>Neck, Abdomen</td>
    <td>4.57</td>
    <td>70.14</td>
    <td>4.75</td>
    <td>67.02</td>
  </tr>
  <tr>
    <td>Linear Regression</td>
    <td>Neck, Biceps, Abdomen, Hip, Thigh</td>
    <td>4.38</td>
    <td>72.53</td>
    <td>4.60</td>
    <td>69.09</td>
  </tr>
  <tr>
    <td>Polynomial Regression degree 3</td>
    <td>Abdomen</td>
    <td>4.56</td>
    <td>70.21</td>
    <td>5.18</td>
    <td>60.89</td>
  </tr>
  <tr>
    <td>Polynomial Regression degree 3</td>
    <td>Neck, Abdomen</td>
    <td>4.36</td>
    <td>72.86</td>
    <td>4.86</td>
    <td>65.54</td>
  </tr>
  <tr>
    <td>Polynomial Regression degree 3</td>
    <td>Neck, Biceps, Abdomen, Hip, Thigh</td>
    <td>3.63</td>
    <td>81.16</td>
    <td>5.14</td>
    <td>61.45</td>
  </tr>
  <tr>
    <td>Polynomial Regression degree 8</td>
    <td>Abdomen</td>
    <td>4.55</td>
    <td>70.33</td>
    <td>5.14</td>
    <td>61.56</td>
  </tr>
  <tr>
    <td>Polynomial Regression degree 8</td>
    <td>Neck, Abdomen</td>
    <td>4.61</td>
    <td>69.60</td>
    <td>6.64</td>
    <td>35.82</td>
  </tr>
  <tr>
    <td>Polynomial Regression degree 8</td>
    <td>Neck, Biceps, Abdomen, Hip, Thigh</td>
    <td>5.25</td>
    <td>1.0</td>
    <td>1566.61</td>
    <td>-35770.51</td>
  </tr>
  <tr>
    <td>Elastic Net degree 8</td>
    <td>Abdomen</td>
    <td>4.56</td>
    <td>70.23</td>
    <td>5.18</td>
    <td>60.91</td>
  </tr>
  <tr>
    <td>Elastic Net degree 8</td>
    <td>Neck, Abdomen</td>
    <td>4.36</td>
    <td>72.82</td>
    <td>4.85</td>
    <td>65.71</td>
  </tr>
  <tr style="background-color: #ffffe0;">
    <td>Elastic Net degree 8</td>
    <td>Neck, Biceps, Abdomen, Hip, Thigh</td>
    <td>4.14</td>
    <td>75.54</td>
    <td>4.52</td>
    <td>70.18</td>
  </tr>
  <tr>
    <td>Pipelined Linear Regression - Poly 4</td>
    <td>Abdomen</td>
    <td>4.56</td>
    <td>70.24</td>
    <td>5.18</td>
    <td>60.88</td>
  </tr>
  <tr>
    <td>Pipelined Linear Regression - Poly 4</td>
    <td>Neck, Abdomen</td>
    <td>4.33</td>
    <td>73.18</td>
    <td>4.85</td>
    <td>65.70</td>
  </tr>
  <tr>
    <td>Pipelined Linear Regression - Poly 4</td>
    <td>Neck, Biceps, Abdomen, Hip, Thigh</td>
    <td>2.77</td>
    <td>89.00</td>
    <td>70.99</td>
    <td>-72.46</td>
  </tr>
</table><br>

The actual vs predicted values plot shows the distribution of the data between the training and test data set for Elastic Net Degree 8. The highest performing model.<br>

![Actual vs Predicted](https://github.com/DesireeEDU/44688-Data-Analytics-Capstone-Project-Desiree-Thompson/blob/main/Actual%20vs%20Predicted%20%20-%20Elastic%20Net%20Degree%208.png)

## Evaluation
The Elastic Net Degree 8 model with features Neck, Biceps, Abdomen, Hip, and
Thigh provided the best performance on the test set with an R2 score of 70.18.
As the goal was to achieve 95% accuracy, the model has not yet reached the
goal. Overall, none of the models showed a high level of over fitting, but did not
meet the goal.


##

**Author:**
Desiree Thompson

**Date Updated:**
July 29, 2024

**Acknowledgments:**
The project utilizes ChatGPT, an AI language model developed by OpenAI, for assistance in writing the README and providing guidance on software engineering practices.
