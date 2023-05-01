We need data from different employees working in different departments, in different organizations. This data must include demographic information like age, gender, employment details. Apart from this we also need the details of the type of workspace the employee is working in which requires data of the supervisors and also the co-workers.We collected the dataset from openml. https://www.openml.org/search?type=data&status=active&id=43674&sort=runs.
This dataset is from a 2014 survey that measures attitudes towards mental health and frequency of mental health disorders in the tech workplace. The survey was conducted by Open Sourcing Mental Illness(OSMI).  

The data contains details like:
Timestamp 
Age 
Gender 
Country state: If you live in the United States, which state or territory do you live in? 
self_employed: Are you self-employed? 
family_history: Do you have a family history of mental illness? 
work_interfere: If you have a mental health condition, do you feel that it interferes with your work? 
no_employees: How many employees does your company or organization have? remote_work: Do you work remotely (outside of an office) at least 50 of the time? tech_company: Is your employer primarily a tech company/organization? 
benefits: Does your employer provide mental health benefits? 
care_options: Do you know the options for mental health care your employer provides? wellness_program: Has your employer ever discussed mental health as part of an employee wellness program?
seek_help: Does your employer provide resources to learn more about mental health issues and how to seek help?
anonymity: Is your anonymity protected if you choose to take advantage of mental health or substance abuse treatment resources?
leave: How easy is it for you to take medical leave for a mental health condition? mentalhealthconsequence: Do you think that discussing a mental health issue with your employer would have negative consequences? 
physhealthconsequence: Do you think that discussing a physical health issue with your employer would have negative consequences? 
coworkers: Would you be willing to discuss a mental health issue with your coworkers? supervisor: Would you be willing to discuss a mental health issue with your direct supervisor(s)? 
mentalhealthinterview: Would you bring up a mental health issue with a potential employer in an interview? 
physhealthinterview: Would you bring up a physical health issue with a potential employer in an interview? 
mentalvsphysical: Do you feel that your employer takes mental health as seriously as physical health?
obs_consequence: Have you heard of or observed negative consequences for coworkers with mental health conditions in your workplace? 
comments: Any additional notes or comments.
treatment: If treatment for a mental health condition is necessary? 
The treatment feature is the target variable for us which will help us build a model to identify people who need to be treated for their mental wellbeing.


After loading the dataset we performed exploratory data analysis using the python programming language and various libraries such as pandas, seaborn and matplotlib After the exploratory data analysis, data pre-processing is performed. The missing values in the numerical features are filled in with the median values since mean values are prone to outliers and the categorical values are filled in with modes. The gender feature which has a lot of distinct values is handled by classifying all of it into male, female, non-binary and others. Features like comments, state and timestamp are removed as more than half of the tuples have null values. 

The data was split into 70-30 percent of the training and test sets. 

We used various classification algorithms, such as Logistic Regression, Naive Bayes, K-Nearest Neighbors, Support Vector Machines, Decision Trees, and Random Forest, to model data collected from a survey conducted in tech firms across the globe to predict whether an individual needs treatment for mental health issues. Since this is a binary classification problem we used logistic regression, based on whether the data is linearly separable or not we should decide to use Support vector machines with a kernel or K-Nearest Neighbors. For all the algorithms Grid Search is used to perform hyper parameter tuning to get the parameters for the data and these values are used to fit the models. We evaluated the performance of these algorithms based on the f1-score and precision. Since this is a medical application the cost of misclassifying a positive observation as a negative is more, for this reason precision is considered as the best performance metric to compare the models.
