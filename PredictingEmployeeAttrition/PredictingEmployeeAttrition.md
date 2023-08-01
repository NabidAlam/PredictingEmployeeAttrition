```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np
sns.set_theme(color_codes=True)
pd.set_option('display.max_columns', None)
```


```python
pip install nbconvert[webpdf]

```

    Requirement already satisfied: nbconvert[webpdf] in c:\users\msn\appdata\local\anaconda3\lib\site-packages (6.5.4)
    Requirement already satisfied: lxml in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbconvert[webpdf]) (4.9.1)
    Requirement already satisfied: jupyterlab-pygments in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbconvert[webpdf]) (0.1.2)
    Requirement already satisfied: jupyter-core>=4.7 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbconvert[webpdf]) (5.2.0)
    Requirement already satisfied: pandocfilters>=1.4.1 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbconvert[webpdf]) (1.5.0)
    Requirement already satisfied: beautifulsoup4 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbconvert[webpdf]) (4.11.1)
    Requirement already satisfied: packaging in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbconvert[webpdf]) (22.0)
    Requirement already satisfied: defusedxml in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbconvert[webpdf]) (0.7.1)
    Requirement already satisfied: entrypoints>=0.2.2 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbconvert[webpdf]) (0.4)
    Requirement already satisfied: pygments>=2.4.1 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbconvert[webpdf]) (2.11.2)
    Requirement already satisfied: jinja2>=3.0 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbconvert[webpdf]) (3.1.2)
    Requirement already satisfied: tinycss2 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbconvert[webpdf]) (1.2.1)
    Requirement already satisfied: mistune<2,>=0.8.1 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbconvert[webpdf]) (0.8.4)
    Requirement already satisfied: bleach in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbconvert[webpdf]) (4.1.0)
    Requirement already satisfied: nbclient>=0.5.0 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbconvert[webpdf]) (0.5.13)
    Requirement already satisfied: nbformat>=5.1 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbconvert[webpdf]) (5.7.0)
    Requirement already satisfied: MarkupSafe>=2.0 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbconvert[webpdf]) (2.1.1)
    Requirement already satisfied: traitlets>=5.0 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbconvert[webpdf]) (5.7.1)
    Collecting pyppeteer<1.1,>=1
      Downloading pyppeteer-1.0.2-py3-none-any.whl (83 kB)
         ---------------------------------------- 83.4/83.4 kB 2.4 MB/s eta 0:00:00
    Requirement already satisfied: pywin32>=1.0 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from jupyter-core>=4.7->nbconvert[webpdf]) (305.1)
    Requirement already satisfied: platformdirs>=2.5 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from jupyter-core>=4.7->nbconvert[webpdf]) (2.5.2)
    Requirement already satisfied: nest-asyncio in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbclient>=0.5.0->nbconvert[webpdf]) (1.5.6)
    Requirement already satisfied: jupyter-client>=6.1.5 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbclient>=0.5.0->nbconvert[webpdf]) (7.3.4)
    Requirement already satisfied: jsonschema>=2.6 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbformat>=5.1->nbconvert[webpdf]) (4.17.3)
    Requirement already satisfied: fastjsonschema in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from nbformat>=5.1->nbconvert[webpdf]) (2.16.2)
    Requirement already satisfied: appdirs<2.0.0,>=1.4.3 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from pyppeteer<1.1,>=1->nbconvert[webpdf]) (1.4.4)
    Requirement already satisfied: urllib3<2.0.0,>=1.25.8 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from pyppeteer<1.1,>=1->nbconvert[webpdf]) (1.26.14)
    Collecting websockets<11.0,>=10.0
      Downloading websockets-10.4-cp310-cp310-win_amd64.whl (101 kB)
         ---------------------------------------- 101.4/101.4 kB ? eta 0:00:00
    Collecting pyee<9.0.0,>=8.1.0
      Downloading pyee-8.2.2-py2.py3-none-any.whl (12 kB)
    Requirement already satisfied: tqdm<5.0.0,>=4.42.1 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from pyppeteer<1.1,>=1->nbconvert[webpdf]) (4.64.1)
    Requirement already satisfied: certifi>=2021 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from pyppeteer<1.1,>=1->nbconvert[webpdf]) (2022.12.7)
    Requirement already satisfied: importlib-metadata>=1.4 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from pyppeteer<1.1,>=1->nbconvert[webpdf]) (4.11.3)
    Requirement already satisfied: soupsieve>1.2 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from beautifulsoup4->nbconvert[webpdf]) (2.3.2.post1)
    Requirement already satisfied: six>=1.9.0 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from bleach->nbconvert[webpdf]) (1.16.0)
    Requirement already satisfied: webencodings in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from bleach->nbconvert[webpdf]) (0.5.1)
    Requirement already satisfied: zipp>=0.5 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from importlib-metadata>=1.4->pyppeteer<1.1,>=1->nbconvert[webpdf]) (3.11.0)
    Requirement already satisfied: pyrsistent!=0.17.0,!=0.17.1,!=0.17.2,>=0.14.0 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from jsonschema>=2.6->nbformat>=5.1->nbconvert[webpdf]) (0.18.0)
    Requirement already satisfied: attrs>=17.4.0 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from jsonschema>=2.6->nbformat>=5.1->nbconvert[webpdf]) (22.1.0)
    Requirement already satisfied: pyzmq>=23.0 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from jupyter-client>=6.1.5->nbclient>=0.5.0->nbconvert[webpdf]) (23.2.0)
    Requirement already satisfied: tornado>=6.0 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from jupyter-client>=6.1.5->nbclient>=0.5.0->nbconvert[webpdf]) (6.1)
    Requirement already satisfied: python-dateutil>=2.8.2 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from jupyter-client>=6.1.5->nbclient>=0.5.0->nbconvert[webpdf]) (2.8.2)
    Requirement already satisfied: colorama in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from tqdm<5.0.0,>=4.42.1->pyppeteer<1.1,>=1->nbconvert[webpdf]) (0.4.6)
    Installing collected packages: pyee, websockets, pyppeteer
    Successfully installed pyee-8.2.2 pyppeteer-1.0.2 websockets-10.4
    Note: you may need to restart the kernel to use updated packages.
    


```python
!jupyter serverextension enable --py nbconvert

```

    Traceback (most recent call last):
      File "C:\Users\msn\AppData\Local\anaconda3\Scripts\jupyter-serverextension-script.py", line 10, in <module>
        sys.exit(main())
      File "C:\Users\msn\AppData\Local\anaconda3\lib\site-packages\jupyter_core\application.py", line 277, in launch_instance
        return super().launch_instance(argv=argv, **kwargs)
      File "C:\Users\msn\AppData\Local\anaconda3\lib\site-packages\traitlets\config\application.py", line 992, in launch_instance
        app.start()
      File "C:\Users\msn\AppData\Local\anaconda3\lib\site-packages\notebook\serverextensions.py", line 289, in start
        super().start()
      File "C:\Users\msn\AppData\Local\anaconda3\lib\site-packages\jupyter_core\application.py", line 266, in start
        self.subapp.start()
      File "C:\Users\msn\AppData\Local\anaconda3\lib\site-packages\notebook\serverextensions.py", line 208, in start
        self.toggle_server_extension_python(arg)
      File "C:\Users\msn\AppData\Local\anaconda3\lib\site-packages\notebook\serverextensions.py", line 197, in toggle_server_extension_python
        m, server_exts = _get_server_extension_metadata(package)
      File "C:\Users\msn\AppData\Local\anaconda3\lib\site-packages\notebook\serverextensions.py", line 325, in _get_server_extension_metadata
        raise KeyError(f'The Python module {module} does not include any valid server extensions')
    KeyError: 'The Python module nbconvert does not include any valid server extensions'
    


```python
import pandas as pd

# Read the CSV file into a DataFrame
df = pd.read_csv('employee.csv')

# Check the first few rows of the DataFrame
df.head()

# Check the number of unique values for each column with object datatype
df.select_dtypes(include='object').nunique()

# Check the number of unique values for each column with int datatype
df.select_dtypes(include='int').nunique()

# Drop columns: 'EmployeeNumber', 'StandardHours', 'Over18', 'PerformanceRating'
df.drop(columns=['EmployeeNumber', 'StandardHours', 'Over18', 'PerformanceRating'], inplace=True)

```


```python
df.select_dtypes(include='int')
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Age</th>
      <th>DailyRate</th>
      <th>DistanceFromHome</th>
      <th>Education</th>
      <th>EmployeeCount</th>
      <th>EnvironmentSatisfaction</th>
      <th>HourlyRate</th>
      <th>JobInvolvement</th>
      <th>JobLevel</th>
      <th>JobSatisfaction</th>
      <th>MonthlyIncome</th>
      <th>MonthlyRate</th>
      <th>NumCompaniesWorked</th>
      <th>PercentSalaryHike</th>
      <th>RelationshipSatisfaction</th>
      <th>StockOptionLevel</th>
      <th>TotalWorkingYears</th>
      <th>TrainingTimesLastYear</th>
      <th>WorkLifeBalance</th>
      <th>YearsAtCompany</th>
      <th>YearsInCurrentRole</th>
      <th>YearsSinceLastPromotion</th>
      <th>YearsWithCurrManager</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>41</td>
      <td>1102</td>
      <td>1</td>
      <td>2</td>
      <td>1</td>
      <td>2</td>
      <td>94</td>
      <td>3</td>
      <td>2</td>
      <td>4</td>
      <td>5993</td>
      <td>19479</td>
      <td>8</td>
      <td>11</td>
      <td>1</td>
      <td>0</td>
      <td>8</td>
      <td>0</td>
      <td>1</td>
      <td>6</td>
      <td>4</td>
      <td>0</td>
      <td>5</td>
    </tr>
    <tr>
      <th>1</th>
      <td>49</td>
      <td>279</td>
      <td>8</td>
      <td>1</td>
      <td>1</td>
      <td>3</td>
      <td>61</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>5130</td>
      <td>24907</td>
      <td>1</td>
      <td>23</td>
      <td>4</td>
      <td>1</td>
      <td>10</td>
      <td>3</td>
      <td>3</td>
      <td>10</td>
      <td>7</td>
      <td>1</td>
      <td>7</td>
    </tr>
    <tr>
      <th>2</th>
      <td>37</td>
      <td>1373</td>
      <td>2</td>
      <td>2</td>
      <td>1</td>
      <td>4</td>
      <td>92</td>
      <td>2</td>
      <td>1</td>
      <td>3</td>
      <td>2090</td>
      <td>2396</td>
      <td>6</td>
      <td>15</td>
      <td>2</td>
      <td>0</td>
      <td>7</td>
      <td>3</td>
      <td>3</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>33</td>
      <td>1392</td>
      <td>3</td>
      <td>4</td>
      <td>1</td>
      <td>4</td>
      <td>56</td>
      <td>3</td>
      <td>1</td>
      <td>3</td>
      <td>2909</td>
      <td>23159</td>
      <td>1</td>
      <td>11</td>
      <td>3</td>
      <td>0</td>
      <td>8</td>
      <td>3</td>
      <td>3</td>
      <td>8</td>
      <td>7</td>
      <td>3</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>27</td>
      <td>591</td>
      <td>2</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>40</td>
      <td>3</td>
      <td>1</td>
      <td>2</td>
      <td>3468</td>
      <td>16632</td>
      <td>9</td>
      <td>12</td>
      <td>4</td>
      <td>1</td>
      <td>6</td>
      <td>3</td>
      <td>3</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1465</th>
      <td>36</td>
      <td>884</td>
      <td>23</td>
      <td>2</td>
      <td>1</td>
      <td>3</td>
      <td>41</td>
      <td>4</td>
      <td>2</td>
      <td>4</td>
      <td>2571</td>
      <td>12290</td>
      <td>4</td>
      <td>17</td>
      <td>3</td>
      <td>1</td>
      <td>17</td>
      <td>3</td>
      <td>3</td>
      <td>5</td>
      <td>2</td>
      <td>0</td>
      <td>3</td>
    </tr>
    <tr>
      <th>1466</th>
      <td>39</td>
      <td>613</td>
      <td>6</td>
      <td>1</td>
      <td>1</td>
      <td>4</td>
      <td>42</td>
      <td>2</td>
      <td>3</td>
      <td>1</td>
      <td>9991</td>
      <td>21457</td>
      <td>4</td>
      <td>15</td>
      <td>1</td>
      <td>1</td>
      <td>9</td>
      <td>5</td>
      <td>3</td>
      <td>7</td>
      <td>7</td>
      <td>1</td>
      <td>7</td>
    </tr>
    <tr>
      <th>1467</th>
      <td>27</td>
      <td>155</td>
      <td>4</td>
      <td>3</td>
      <td>1</td>
      <td>2</td>
      <td>87</td>
      <td>4</td>
      <td>2</td>
      <td>2</td>
      <td>6142</td>
      <td>5174</td>
      <td>1</td>
      <td>20</td>
      <td>2</td>
      <td>1</td>
      <td>6</td>
      <td>0</td>
      <td>3</td>
      <td>6</td>
      <td>2</td>
      <td>0</td>
      <td>3</td>
    </tr>
    <tr>
      <th>1468</th>
      <td>49</td>
      <td>1023</td>
      <td>2</td>
      <td>3</td>
      <td>1</td>
      <td>4</td>
      <td>63</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>5390</td>
      <td>13243</td>
      <td>2</td>
      <td>14</td>
      <td>4</td>
      <td>0</td>
      <td>17</td>
      <td>3</td>
      <td>2</td>
      <td>9</td>
      <td>6</td>
      <td>0</td>
      <td>8</td>
    </tr>
    <tr>
      <th>1469</th>
      <td>34</td>
      <td>628</td>
      <td>8</td>
      <td>3</td>
      <td>1</td>
      <td>2</td>
      <td>82</td>
      <td>4</td>
      <td>2</td>
      <td>3</td>
      <td>4404</td>
      <td>10228</td>
      <td>2</td>
      <td>12</td>
      <td>1</td>
      <td>0</td>
      <td>6</td>
      <td>3</td>
      <td>4</td>
      <td>4</td>
      <td>3</td>
      <td>1</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
<p>1470 rows × 23 columns</p>
</div>




```python
# Get the names of all columns with data type 'int'
int_vars = df.select_dtypes(include='int').columns.tolist()

# Create a figure with subplots
num_cols = len(int_vars)
num_rows = (num_cols + 2) // 3  # To make sure there are enough rows for the subplots
fig, axs = plt.subplots(nrows=num_rows, ncols=3, figsize=(15, 5*num_rows))
axs = axs.flatten()

# Create a histogram for each integer variable
for i, var in enumerate(int_vars):
    df[var].plot.hist(ax=axs[i])
    axs[i].set_title(var)

# Remove any extra empty subplots if needed
if num_cols < len(axs):
    for i in range(num_cols, len(axs)):
        fig.delaxes(axs[i])

# Adjust spacing between subplots
fig.tight_layout()

# Show plot
plt.show()
```


    
![png](output_5_0.png)
    



```python
# Get the names of all columns with data type 'int'
int_vars = df.select_dtypes(include='int').columns.tolist()

# Create a figure with subplots
num_cols = len(int_vars)
num_rows = (num_cols + 2) // 3  # To make sure there are enough rows for the subplots
fig, axs = plt.subplots(nrows=num_rows, ncols=3, figsize=(15, 5*num_rows))
axs = axs.flatten()

# Create a box plot for each integer variable using Seaborn
for i, var in enumerate(int_vars):
    sns.boxplot(x=df[var], ax=axs[i])
    axs[i].set_title(var)

# Remove any extra empty subplots if needed
if num_cols < len(axs):
    for i in range(num_cols, len(axs)):
        fig.delaxes(axs[i])

# Adjust spacing between subplots
fig.tight_layout()

# Show plot
plt.show()
```


    
![png](output_6_0.png)
    



```python
# Filter columns with data type 'int'
int_columns = df.select_dtypes(include='int')


mean_values = int_columns.mean()
std_values = int_columns.std()
min_values = int_columns.min()
q1_values = int_columns.quantile(0.25)
q2_values = int_columns.quantile(0.5)
q3_values = int_columns.quantile(0.75)
iqr_values = q3_values - q1_values
max_values = int_columns.max()
statistics_df = pd.DataFrame({
    'Mean': mean_values,
    'Std': std_values,
    'Min': min_values,
    'Q1': q1_values,
    'Q2 (Median)': q2_values,
    'Q3': q3_values,
    'IQR': iqr_values,
    'Max': max_values
})

statistics_df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Mean</th>
      <th>Std</th>
      <th>Min</th>
      <th>Q1</th>
      <th>Q2 (Median)</th>
      <th>Q3</th>
      <th>IQR</th>
      <th>Max</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Age</th>
      <td>36.923810</td>
      <td>9.135373e+00</td>
      <td>18</td>
      <td>30.0</td>
      <td>36.0</td>
      <td>43.00</td>
      <td>13.00</td>
      <td>60</td>
    </tr>
    <tr>
      <th>DailyRate</th>
      <td>802.485714</td>
      <td>4.035091e+02</td>
      <td>102</td>
      <td>465.0</td>
      <td>802.0</td>
      <td>1157.00</td>
      <td>692.00</td>
      <td>1499</td>
    </tr>
    <tr>
      <th>DistanceFromHome</th>
      <td>9.192517</td>
      <td>8.106864e+00</td>
      <td>1</td>
      <td>2.0</td>
      <td>7.0</td>
      <td>14.00</td>
      <td>12.00</td>
      <td>29</td>
    </tr>
    <tr>
      <th>Education</th>
      <td>2.912925</td>
      <td>1.024165e+00</td>
      <td>1</td>
      <td>2.0</td>
      <td>3.0</td>
      <td>4.00</td>
      <td>2.00</td>
      <td>5</td>
    </tr>
    <tr>
      <th>EmployeeCount</th>
      <td>1.000000</td>
      <td>1.110601e-16</td>
      <td>1</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.00</td>
      <td>0.00</td>
      <td>1</td>
    </tr>
    <tr>
      <th>EnvironmentSatisfaction</th>
      <td>2.721769</td>
      <td>1.093082e+00</td>
      <td>1</td>
      <td>2.0</td>
      <td>3.0</td>
      <td>4.00</td>
      <td>2.00</td>
      <td>4</td>
    </tr>
    <tr>
      <th>HourlyRate</th>
      <td>65.891156</td>
      <td>2.032943e+01</td>
      <td>30</td>
      <td>48.0</td>
      <td>66.0</td>
      <td>83.75</td>
      <td>35.75</td>
      <td>100</td>
    </tr>
    <tr>
      <th>JobInvolvement</th>
      <td>2.729932</td>
      <td>7.115611e-01</td>
      <td>1</td>
      <td>2.0</td>
      <td>3.0</td>
      <td>3.00</td>
      <td>1.00</td>
      <td>4</td>
    </tr>
    <tr>
      <th>JobLevel</th>
      <td>2.063946</td>
      <td>1.106940e+00</td>
      <td>1</td>
      <td>1.0</td>
      <td>2.0</td>
      <td>3.00</td>
      <td>2.00</td>
      <td>5</td>
    </tr>
    <tr>
      <th>JobSatisfaction</th>
      <td>2.728571</td>
      <td>1.102846e+00</td>
      <td>1</td>
      <td>2.0</td>
      <td>3.0</td>
      <td>4.00</td>
      <td>2.00</td>
      <td>4</td>
    </tr>
    <tr>
      <th>MonthlyIncome</th>
      <td>6502.931293</td>
      <td>4.707957e+03</td>
      <td>1009</td>
      <td>2911.0</td>
      <td>4919.0</td>
      <td>8379.00</td>
      <td>5468.00</td>
      <td>19999</td>
    </tr>
    <tr>
      <th>MonthlyRate</th>
      <td>14313.103401</td>
      <td>7.117786e+03</td>
      <td>2094</td>
      <td>8047.0</td>
      <td>14235.5</td>
      <td>20461.50</td>
      <td>12414.50</td>
      <td>26999</td>
    </tr>
    <tr>
      <th>NumCompaniesWorked</th>
      <td>2.693197</td>
      <td>2.498009e+00</td>
      <td>0</td>
      <td>1.0</td>
      <td>2.0</td>
      <td>4.00</td>
      <td>3.00</td>
      <td>9</td>
    </tr>
    <tr>
      <th>PercentSalaryHike</th>
      <td>15.209524</td>
      <td>3.659938e+00</td>
      <td>11</td>
      <td>12.0</td>
      <td>14.0</td>
      <td>18.00</td>
      <td>6.00</td>
      <td>25</td>
    </tr>
    <tr>
      <th>RelationshipSatisfaction</th>
      <td>2.712245</td>
      <td>1.081209e+00</td>
      <td>1</td>
      <td>2.0</td>
      <td>3.0</td>
      <td>4.00</td>
      <td>2.00</td>
      <td>4</td>
    </tr>
    <tr>
      <th>StockOptionLevel</th>
      <td>0.793878</td>
      <td>8.520767e-01</td>
      <td>0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>3</td>
    </tr>
    <tr>
      <th>TotalWorkingYears</th>
      <td>11.279592</td>
      <td>7.780782e+00</td>
      <td>0</td>
      <td>6.0</td>
      <td>10.0</td>
      <td>15.00</td>
      <td>9.00</td>
      <td>40</td>
    </tr>
    <tr>
      <th>TrainingTimesLastYear</th>
      <td>2.799320</td>
      <td>1.289271e+00</td>
      <td>0</td>
      <td>2.0</td>
      <td>3.0</td>
      <td>3.00</td>
      <td>1.00</td>
      <td>6</td>
    </tr>
    <tr>
      <th>WorkLifeBalance</th>
      <td>2.761224</td>
      <td>7.064758e-01</td>
      <td>1</td>
      <td>2.0</td>
      <td>3.0</td>
      <td>3.00</td>
      <td>1.00</td>
      <td>4</td>
    </tr>
    <tr>
      <th>YearsAtCompany</th>
      <td>7.008163</td>
      <td>6.126525e+00</td>
      <td>0</td>
      <td>3.0</td>
      <td>5.0</td>
      <td>9.00</td>
      <td>6.00</td>
      <td>40</td>
    </tr>
    <tr>
      <th>YearsInCurrentRole</th>
      <td>4.229252</td>
      <td>3.623137e+00</td>
      <td>0</td>
      <td>2.0</td>
      <td>3.0</td>
      <td>7.00</td>
      <td>5.00</td>
      <td>18</td>
    </tr>
    <tr>
      <th>YearsSinceLastPromotion</th>
      <td>2.187755</td>
      <td>3.222430e+00</td>
      <td>0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>3.00</td>
      <td>3.00</td>
      <td>15</td>
    </tr>
    <tr>
      <th>YearsWithCurrManager</th>
      <td>4.123129</td>
      <td>3.568136e+00</td>
      <td>0</td>
      <td>2.0</td>
      <td>3.0</td>
      <td>7.00</td>
      <td>5.00</td>
      <td>17</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Filter columns with data type 'int'
int_columns = df.select_dtypes(include='int')
q1_values = int_columns.quantile(0.25)
q3_values = int_columns.quantile(0.75)
iqr_values = q3_values - q1_values
upper_whisker_values = q3_values + 1.5 * iqr_values
lower_whisker_values = q1_values - 1.5 * iqr_values

whisker_df = pd.DataFrame({
    'Upper Whisker': upper_whisker_values,
    'Lower Whisker': lower_whisker_values
})

whisker_df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Upper Whisker</th>
      <th>Lower Whisker</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Age</th>
      <td>62.500</td>
      <td>10.500</td>
    </tr>
    <tr>
      <th>DailyRate</th>
      <td>2195.000</td>
      <td>-573.000</td>
    </tr>
    <tr>
      <th>DistanceFromHome</th>
      <td>32.000</td>
      <td>-16.000</td>
    </tr>
    <tr>
      <th>Education</th>
      <td>7.000</td>
      <td>-1.000</td>
    </tr>
    <tr>
      <th>EmployeeCount</th>
      <td>1.000</td>
      <td>1.000</td>
    </tr>
    <tr>
      <th>EnvironmentSatisfaction</th>
      <td>7.000</td>
      <td>-1.000</td>
    </tr>
    <tr>
      <th>HourlyRate</th>
      <td>137.375</td>
      <td>-5.625</td>
    </tr>
    <tr>
      <th>JobInvolvement</th>
      <td>4.500</td>
      <td>0.500</td>
    </tr>
    <tr>
      <th>JobLevel</th>
      <td>6.000</td>
      <td>-2.000</td>
    </tr>
    <tr>
      <th>JobSatisfaction</th>
      <td>7.000</td>
      <td>-1.000</td>
    </tr>
    <tr>
      <th>MonthlyIncome</th>
      <td>16581.000</td>
      <td>-5291.000</td>
    </tr>
    <tr>
      <th>MonthlyRate</th>
      <td>39083.250</td>
      <td>-10574.750</td>
    </tr>
    <tr>
      <th>NumCompaniesWorked</th>
      <td>8.500</td>
      <td>-3.500</td>
    </tr>
    <tr>
      <th>PercentSalaryHike</th>
      <td>27.000</td>
      <td>3.000</td>
    </tr>
    <tr>
      <th>RelationshipSatisfaction</th>
      <td>7.000</td>
      <td>-1.000</td>
    </tr>
    <tr>
      <th>StockOptionLevel</th>
      <td>2.500</td>
      <td>-1.500</td>
    </tr>
    <tr>
      <th>TotalWorkingYears</th>
      <td>28.500</td>
      <td>-7.500</td>
    </tr>
    <tr>
      <th>TrainingTimesLastYear</th>
      <td>4.500</td>
      <td>0.500</td>
    </tr>
    <tr>
      <th>WorkLifeBalance</th>
      <td>4.500</td>
      <td>0.500</td>
    </tr>
    <tr>
      <th>YearsAtCompany</th>
      <td>18.000</td>
      <td>-6.000</td>
    </tr>
    <tr>
      <th>YearsInCurrentRole</th>
      <td>14.500</td>
      <td>-5.500</td>
    </tr>
    <tr>
      <th>YearsSinceLastPromotion</th>
      <td>7.500</td>
      <td>-4.500</td>
    </tr>
    <tr>
      <th>YearsWithCurrManager</th>
      <td>14.500</td>
      <td>-5.500</td>
    </tr>
  </tbody>
</table>
</div>




```python
import pandas as pd

# Assuming you already have the DataFrame 'df' containing the data

# Filter columns with data type 'int'
int_columns = df.select_dtypes(include='int')

q1_values = int_columns.quantile(0.25)
q3_values = int_columns.quantile(0.75)
iqr_values = q3_values - q1_values
upper_whisker_values = q3_values + 1.5 * iqr_values
lower_whisker_values = q1_values - 1.5 * iqr_values

outlier_count = ((int_columns < lower_whisker_values) | (int_columns > upper_whisker_values)).sum()
total_data_points = len(int_columns)
outlier_proportion = (outlier_count / total_data_points) * 100

outlier_list = {}
for col in int_columns.columns:
    outliers = int_columns[col][(int_columns[col] < lower_whisker_values[col]) | (int_columns[col] > upper_whisker_values[col])].tolist()
    outlier_list[col] = outliers

outlier_df = pd.DataFrame({
    'Outlier Count': outlier_count,
    'Outlier Proportion (%)': outlier_proportion,
    'Outlier List': outlier_list
})

outlier_df

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Outlier Count</th>
      <th>Outlier Proportion (%)</th>
      <th>Outlier List</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Age</th>
      <td>0</td>
      <td>0.000000</td>
      <td>[]</td>
    </tr>
    <tr>
      <th>DailyRate</th>
      <td>0</td>
      <td>0.000000</td>
      <td>[]</td>
    </tr>
    <tr>
      <th>DistanceFromHome</th>
      <td>0</td>
      <td>0.000000</td>
      <td>[]</td>
    </tr>
    <tr>
      <th>Education</th>
      <td>0</td>
      <td>0.000000</td>
      <td>[]</td>
    </tr>
    <tr>
      <th>EmployeeCount</th>
      <td>0</td>
      <td>0.000000</td>
      <td>[]</td>
    </tr>
    <tr>
      <th>EnvironmentSatisfaction</th>
      <td>0</td>
      <td>0.000000</td>
      <td>[]</td>
    </tr>
    <tr>
      <th>HourlyRate</th>
      <td>0</td>
      <td>0.000000</td>
      <td>[]</td>
    </tr>
    <tr>
      <th>JobInvolvement</th>
      <td>0</td>
      <td>0.000000</td>
      <td>[]</td>
    </tr>
    <tr>
      <th>JobLevel</th>
      <td>0</td>
      <td>0.000000</td>
      <td>[]</td>
    </tr>
    <tr>
      <th>JobSatisfaction</th>
      <td>0</td>
      <td>0.000000</td>
      <td>[]</td>
    </tr>
    <tr>
      <th>MonthlyIncome</th>
      <td>114</td>
      <td>7.755102</td>
      <td>[19094, 18947, 19545, 18740, 18844, 18172, 173...</td>
    </tr>
    <tr>
      <th>MonthlyRate</th>
      <td>0</td>
      <td>0.000000</td>
      <td>[]</td>
    </tr>
    <tr>
      <th>NumCompaniesWorked</th>
      <td>52</td>
      <td>3.537415</td>
      <td>[9, 9, 9, 9, 9, 9, 9, 9, 9, 9, 9, 9, 9, 9, 9, ...</td>
    </tr>
    <tr>
      <th>PercentSalaryHike</th>
      <td>0</td>
      <td>0.000000</td>
      <td>[]</td>
    </tr>
    <tr>
      <th>RelationshipSatisfaction</th>
      <td>0</td>
      <td>0.000000</td>
      <td>[]</td>
    </tr>
    <tr>
      <th>StockOptionLevel</th>
      <td>85</td>
      <td>5.782313</td>
      <td>[3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, ...</td>
    </tr>
    <tr>
      <th>TotalWorkingYears</th>
      <td>63</td>
      <td>4.285714</td>
      <td>[31, 29, 37, 38, 30, 40, 36, 34, 32, 33, 37, 3...</td>
    </tr>
    <tr>
      <th>TrainingTimesLastYear</th>
      <td>238</td>
      <td>16.190476</td>
      <td>[0, 5, 5, 5, 6, 5, 5, 5, 6, 6, 0, 0, 0, 5, 0, ...</td>
    </tr>
    <tr>
      <th>WorkLifeBalance</th>
      <td>0</td>
      <td>0.000000</td>
      <td>[]</td>
    </tr>
    <tr>
      <th>YearsAtCompany</th>
      <td>104</td>
      <td>7.074830</td>
      <td>[25, 22, 22, 27, 21, 22, 37, 25, 20, 40, 20, 2...</td>
    </tr>
    <tr>
      <th>YearsInCurrentRole</th>
      <td>21</td>
      <td>1.428571</td>
      <td>[15, 16, 18, 15, 18, 17, 16, 15, 16, 15, 16, 1...</td>
    </tr>
    <tr>
      <th>YearsSinceLastPromotion</th>
      <td>107</td>
      <td>7.278912</td>
      <td>[8, 15, 8, 8, 9, 13, 12, 10, 11, 9, 12, 15, 15...</td>
    </tr>
    <tr>
      <th>YearsWithCurrManager</th>
      <td>14</td>
      <td>0.952381</td>
      <td>[17, 15, 15, 15, 15, 17, 16, 17, 15, 17, 17, 1...</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Get the names of all columns with data type 'object' (categorical columns)
cat_vars = df.select_dtypes(include='object').columns.tolist()

# Create a figure with subplots
num_cols = len(cat_vars)
num_rows = (num_cols + 2) // 3  # To make sure there are enough rows for the subplots
fig, axs = plt.subplots(nrows=num_rows, ncols=3, figsize=(15, 5*num_rows))
axs = axs.flatten()

# Create a countplot for each categorical variable using Seaborn
for i, var in enumerate(cat_vars):
    sns.countplot(x=var, data=df, ax=axs[i])
    axs[i].set_title(var)
    axs[i].tick_params(axis='x', rotation=90)  # Rotate x-axis labels for readability

# Remove any extra empty subplots if needed
if num_cols < len(axs):
    for i in range(num_cols, len(axs)):
        fig.delaxes(axs[i])

# Adjust spacing between subplots
fig.tight_layout()

# Show plot
plt.show()
```


    
![png](output_10_0.png)
    



```python
# Create a dictionary to store unique categories and their frequencies for each column
unique_categories = {}

# Iterate over each column in the DataFrame
for col in df.columns:
    # Check if the column has object data type (categorical column)
    if df[col].dtype == 'object':
        value_counts = df[col].value_counts()
        unique_categories[col] = {
            'Categories': value_counts.index.tolist(),
            'Frequency': value_counts.values.tolist()
        }

# Display the list of unique categories and their frequencies for each column
for col, data in unique_categories.items():
    print(f"Column: {col}")
    print(pd.DataFrame(data))
    print()
```

    Column: Attrition
      Categories  Frequency
    0         No       1233
    1        Yes        237
    
    Column: BusinessTravel
              Categories  Frequency
    0      Travel_Rarely       1043
    1  Travel_Frequently        277
    2         Non-Travel        150
    
    Column: Department
                   Categories  Frequency
    0  Research & Development        961
    1                   Sales        446
    2         Human Resources         63
    
    Column: EducationField
             Categories  Frequency
    0     Life Sciences        606
    1           Medical        464
    2         Marketing        159
    3  Technical Degree        132
    4             Other         82
    5   Human Resources         27
    
    Column: Gender
      Categories  Frequency
    0       Male        882
    1     Female        588
    
    Column: JobRole
                      Categories  Frequency
    0            Sales Executive        326
    1         Research Scientist        292
    2      Laboratory Technician        259
    3     Manufacturing Director        145
    4  Healthcare Representative        131
    5                    Manager        102
    6       Sales Representative         83
    7          Research Director         80
    8            Human Resources         52
    
    Column: MaritalStatus
      Categories  Frequency
    0    Married        673
    1     Single        470
    2   Divorced        327
    
    Column: OverTime
      Categories  Frequency
    0         No       1054
    1        Yes        416
    
    


```python
# Get the names of all columns with data type 'int'
int_vars = df.select_dtypes(include='int').columns.tolist()

# Create a figure with subplots
num_cols = len(int_vars)
num_rows = (num_cols + 2) // 3  # To make sure there are enough rows for the subplots
fig, axs = plt.subplots(nrows=num_rows, ncols=3, figsize=(15, 5*num_rows))
axs = axs.flatten()

# Create a box plot for each integer variable using Seaborn with hue='attrition'
for i, var in enumerate(int_vars):
    sns.boxplot(y=var, x='Attrition', data=df, ax=axs[i])
    axs[i].set_title(var)

# Remove any extra empty subplots if needed
if num_cols < len(axs):
    for i in range(num_cols, len(axs)):
        fig.delaxes(axs[i])

# Adjust spacing between subplots
fig.tight_layout()

# Show plot
plt.show()
```


    
![png](output_12_0.png)
    



```python
# Get the names of all columns with data type 'int'
int_vars = df.select_dtypes(include='int').columns.tolist()

# Create a figure with subplots
num_cols = len(int_vars)
num_rows = (num_cols + 2) // 3  # To make sure there are enough rows for the subplots
fig, axs = plt.subplots(nrows=num_rows, ncols=3, figsize=(15, 5*num_rows))
axs = axs.flatten()

# Create a histogram for each integer variable with hue='Attrition'
for i, var in enumerate(int_vars):
    sns.histplot(data=df, x=var, hue='Attrition', kde=True, ax=axs[i])
    axs[i].set_title(var)

# Remove any extra empty subplots if needed
if num_cols < len(axs):
    for i in range(num_cols, len(axs)):
        fig.delaxes(axs[i])

# Adjust spacing between subplots
fig.tight_layout()

# Show plot
plt.show()
```


    ---------------------------------------------------------------------------

    LinAlgError                               Traceback (most recent call last)

    File ~\AppData\Local\anaconda3\lib\site-packages\scipy\stats\_kde.py:223, in gaussian_kde.__init__(self, dataset, bw_method, weights)
        222 try:
    --> 223     self.set_bandwidth(bw_method=bw_method)
        224 except linalg.LinAlgError as e:
    

    File ~\AppData\Local\anaconda3\lib\site-packages\scipy\stats\_kde.py:571, in gaussian_kde.set_bandwidth(self, bw_method)
        569     raise ValueError(msg)
    --> 571 self._compute_covariance()
    

    File ~\AppData\Local\anaconda3\lib\site-packages\scipy\stats\_kde.py:583, in gaussian_kde._compute_covariance(self)
        580     self._data_covariance = atleast_2d(cov(self.dataset, rowvar=1,
        581                                        bias=False,
        582                                        aweights=self.weights))
    --> 583     self._data_cho_cov = linalg.cholesky(self._data_covariance,
        584                                          lower=True)
        586 self.covariance = self._data_covariance * self.factor**2
    

    File ~\AppData\Local\anaconda3\lib\site-packages\scipy\linalg\_decomp_cholesky.py:89, in cholesky(a, lower, overwrite_a, check_finite)
         46 """
         47 Compute the Cholesky decomposition of a matrix.
         48 
       (...)
         87 
         88 """
    ---> 89 c, lower = _cholesky(a, lower=lower, overwrite_a=overwrite_a, clean=True,
         90                      check_finite=check_finite)
         91 return c
    

    File ~\AppData\Local\anaconda3\lib\site-packages\scipy\linalg\_decomp_cholesky.py:37, in _cholesky(a, lower, overwrite_a, clean, check_finite)
         36 if info > 0:
    ---> 37     raise LinAlgError("%d-th leading minor of the array is not positive "
         38                       "definite" % info)
         39 if info < 0:
    

    LinAlgError: 1-th leading minor of the array is not positive definite

    
    The above exception was the direct cause of the following exception:
    

    LinAlgError                               Traceback (most recent call last)

    Cell In[249], line 12
         10 # Create a histogram for each integer variable with hue='Attrition'
         11 for i, var in enumerate(int_vars):
    ---> 12     sns.histplot(data=df, x=var, hue='Attrition', kde=True, ax=axs[i])
         13     axs[i].set_title(var)
         15 # Remove any extra empty subplots if needed
    

    File ~\AppData\Local\anaconda3\lib\site-packages\seaborn\distributions.py:1432, in histplot(data, x, y, hue, weights, stat, bins, binwidth, binrange, discrete, cumulative, common_bins, common_norm, multiple, element, fill, shrink, kde, kde_kws, line_kws, thresh, pthresh, pmax, cbar, cbar_ax, cbar_kws, palette, hue_order, hue_norm, color, log_scale, legend, ax, **kwargs)
       1421 estimate_kws = dict(
       1422     stat=stat,
       1423     bins=bins,
       (...)
       1427     cumulative=cumulative,
       1428 )
       1430 if p.univariate:
    -> 1432     p.plot_univariate_histogram(
       1433         multiple=multiple,
       1434         element=element,
       1435         fill=fill,
       1436         shrink=shrink,
       1437         common_norm=common_norm,
       1438         common_bins=common_bins,
       1439         kde=kde,
       1440         kde_kws=kde_kws,
       1441         color=color,
       1442         legend=legend,
       1443         estimate_kws=estimate_kws,
       1444         line_kws=line_kws,
       1445         **kwargs,
       1446     )
       1448 else:
       1450     p.plot_bivariate_histogram(
       1451         common_bins=common_bins,
       1452         common_norm=common_norm,
       (...)
       1462         **kwargs,
       1463     )
    

    File ~\AppData\Local\anaconda3\lib\site-packages\seaborn\distributions.py:451, in _DistributionPlotter.plot_univariate_histogram(self, multiple, element, fill, common_norm, common_bins, shrink, kde, kde_kws, color, legend, line_kws, estimate_kws, **plot_kws)
        449     kde_kws["cumulative"] = estimate_kws["cumulative"]
        450     log_scale = self._log_scaled(self.data_variable)
    --> 451     densities = self._compute_univariate_density(
        452         self.data_variable,
        453         common_norm,
        454         common_bins,
        455         kde_kws,
        456         log_scale,
        457         warn_singular=False,
        458     )
        460 # First pass through the data to compute the histograms
        461 for sub_vars, sub_data in self.iter_data("hue", from_comp_data=True):
        462 
        463     # Prepare the relevant data
    

    File ~\AppData\Local\anaconda3\lib\site-packages\seaborn\distributions.py:317, in _DistributionPlotter._compute_univariate_density(self, data_variable, common_norm, common_grid, estimate_kws, log_scale, warn_singular)
        315     if common_grid:
        316         all_observations = self.comp_data.dropna()
    --> 317         estimator.define_support(all_observations[data_variable])
        318 else:
        319     common_norm = False
    

    File ~\AppData\Local\anaconda3\lib\site-packages\seaborn\_statistics.py:127, in KDE.define_support(self, x1, x2, weights, cache)
        125 """Create the evaluation grid for a given data set."""
        126 if x2 is None:
    --> 127     support = self._define_support_univariate(x1, weights)
        128 else:
        129     support = self._define_support_bivariate(x1, x2, weights)
    

    File ~\AppData\Local\anaconda3\lib\site-packages\seaborn\_statistics.py:99, in KDE._define_support_univariate(self, x, weights)
         97 def _define_support_univariate(self, x, weights):
         98     """Create a 1D grid of evaluation points."""
    ---> 99     kde = self._fit(x, weights)
        100     bw = np.sqrt(kde.covariance.squeeze())
        101     grid = self._define_support_grid(
        102         x, bw, self.cut, self.clip, self.gridsize
        103     )
    

    File ~\AppData\Local\anaconda3\lib\site-packages\seaborn\_statistics.py:142, in KDE._fit(self, fit_data, weights)
        139 if weights is not None:
        140     fit_kws["weights"] = weights
    --> 142 kde = gaussian_kde(fit_data, **fit_kws)
        143 kde.set_bandwidth(kde.factor * self.bw_adjust)
        145 return kde
    

    File ~\AppData\Local\anaconda3\lib\site-packages\scipy\stats\_kde.py:232, in gaussian_kde.__init__(self, dataset, bw_method, weights)
        224 except linalg.LinAlgError as e:
        225     msg = ("The data appears to lie in a lower-dimensional subspace "
        226            "of the space in which it is expressed. This has resulted "
        227            "in a singular data covariance matrix, which cannot be "
       (...)
        230            "analysis / dimensionality reduction and using "
        231            "`gaussian_kde` with the transformed data.")
    --> 232     raise linalg.LinAlgError(msg) from e
    

    LinAlgError: The data appears to lie in a lower-dimensional subspace of the space in which it is expressed. This has resulted in a singular data covariance matrix, which cannot be treated using the algorithms implemented in `gaussian_kde`. Consider performing principle component analysis / dimensionality reduction and using `gaussian_kde` with the transformed data.



    
![png](output_13_1.png)
    



```python
# Get the names of all columns with data type 'object' (categorical columns)
cat_vars = df.select_dtypes(include='object').columns.tolist()

# Create a figure with subplots
num_cols = len(cat_vars)
num_rows = (num_cols + 2) // 3  # To make sure there are enough rows for the subplots
fig, axs = plt.subplots(nrows=num_rows, ncols=3, figsize=(15, 5*num_rows))
axs = axs.flatten()

# Create a countplot for each categorical variable using Seaborn with 'Attrition' as hue
for i, var in enumerate(cat_vars):
    sns.countplot(x=var, hue='Attrition', data=df, ax=axs[i])
    axs[i].set_title(var)
    axs[i].tick_params(axis='x', rotation=90)  # Rotate x-axis labels for readability

# Remove any extra empty subplots if needed
if num_cols < len(axs):
    for i in range(num_cols, len(axs)):
        fig.delaxes(axs[i])

# Adjust spacing between subplots
fig.tight_layout()

# Show plot
plt.show()

```


    
![png](output_14_0.png)
    



```python
import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd

# Assuming you already have the DataFrame 'df' containing the data

# Get the names of all columns with data type 'object' (categorical columns)
cat_vars = df.select_dtypes(include='object').columns.tolist()

# Create the stacked density plot
num_cols = len(cat_vars)
num_rows = (num_cols + 2) // 3
fig, axs = plt.subplots(nrows=num_rows, ncols=3, figsize=(15, 5*num_rows))
axs = axs.flatten()

for i, var in enumerate(cat_vars):
    sns.histplot(data=df, x=var, hue='Attrition', stat='density', multiple='stack', ax=axs[i])
    axs[i].set_title(var)
    axs[i].set_ylabel('Density')
    axs[i].tick_params(axis='x', rotation=90)

# Remove any extra empty subplots if needed
if num_cols < len(axs):
    for i in range(num_cols, len(axs)):
        fig.delaxes(axs[i])

# Adjust spacing between subplots
fig.tight_layout()

# Show plot
plt.show()
```


    
![png](output_15_0.png)
    



```python
from scipy.stats import ttest_ind

# Extract 'Total Working Years' for employees who left (Attrition = 'Yes') and stayed (Attrition = 'No')
working_years_left = df[df['Attrition'] == 'Yes']['TotalWorkingYears']
working_years_stayed = df[df['Attrition'] == 'No']['TotalWorkingYears']

# Perform the independent t-test
alpha = 0.05
t_statistic, p_value = ttest_ind(working_years_left, working_years_stayed)

# Print the results
print("Independent T-Test Results:")
print(f"T-Statistic: {t_statistic}")
print(f"P-Value: {p_value}")
```

    Independent T-Test Results:
    T-Statistic: -6.6522546135024445
    P-Value: 4.0618781112668525e-11
    


```python
from scipy.stats import f_oneway

# Extract 'Age' for employees from each department
age_Sales = df[df['Department'] == 'Sales']['Age']
age_Research_Development = df[df['Department'] == 'Research & Development']['Age']
age_Human_Resources = df[df['Department'] == 'Human Resources']['Age']

# Perform the one-way ANOVA
alpha = 0.05
f_statistic, p_value = f_oneway(age_Sales, age_Research_Development, age_Human_Resources)

# Print the results
print("One-Way ANOVA Results:")
print(f"F-Statistic: {f_statistic}")
print(f"P-Value: {p_value}")
```

    One-Way ANOVA Results:
    F-Statistic: 0.7655031924976903
    P-Value: 0.46528552999349515
    


```python
#Check missing value
check_missing = df.isnull().sum() * 100 / df.shape[0]
check_missing[check_missing > 0].sort_values(ascending=False)
```




    Series([], dtype: float64)




```python
# Loop over each column in the DataFrame where dtype is 'object'
for col in df.select_dtypes(include=['object']).columns:

    # Print the column name and the unique values
    print(f"{col}: {df[col].unique()}")
```

    Attrition: ['Yes' 'No']
    BusinessTravel: ['Travel_Rarely' 'Travel_Frequently' 'Non-Travel']
    Department: ['Sales' 'Research & Development' 'Human Resources']
    EducationField: ['Life Sciences' 'Other' 'Medical' 'Marketing' 'Technical Degree'
     'Human Resources']
    Gender: ['Female' 'Male']
    JobRole: ['Sales Executive' 'Research Scientist' 'Laboratory Technician'
     'Manufacturing Director' 'Healthcare Representative' 'Manager'
     'Sales Representative' 'Research Director' 'Human Resources']
    MaritalStatus: ['Single' 'Married' 'Divorced']
    OverTime: ['Yes' 'No']
    


```python
from sklearn import preprocessing

# Loop over each column in the DataFrame where dtype is 'object'
for col in df.select_dtypes(include=['object']).columns:

    # Initialize a LabelEncoder object
    label_encoder = preprocessing.LabelEncoder()

    # Fit the encoder to the unique values in the column
    label_encoder.fit(df[col].unique())

    # Transform the column using the encoder
    df[col] = label_encoder.transform(df[col])

    # Print the column name and the unique encoded values
    print(f"{col}: {df[col].unique()}")
```

    Attrition: [1 0]
    BusinessTravel: [2 1 0]
    Department: [2 1 0]
    EducationField: [1 4 3 2 5 0]
    Gender: [0 1]
    JobRole: [7 6 2 4 0 3 8 5 1]
    MaritalStatus: [2 1 0]
    OverTime: [1 0]
    


```python
#Correlation Heatmap
plt.figure(figsize=(20, 16))
sns.heatmap(df.corr(), fmt='.2g')
```




    <Axes: >




    
![png](output_21_1.png)
    



```python
X = df.drop('Attrition', axis=1)
y = df['Attrition']
```


```python
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, stratify=y, random_state=0)
```


```python
from scipy import stats

# Define the columns for which you want to remove outliers
selected_columns = ['MonthlyIncome', 'StockOptionLevel', 'TotalWorkingYears', 'TrainingTimesLastYear', 'YearsAtCompany',
                    'YearsInCurrentRole', 'YearsSinceLastPromotion', 'YearsWithCurrManager']

# Calculate the Z-scores for the selected columns in the training data
z_scores = np.abs(stats.zscore(X_train[selected_columns]))

# Set a threshold value for outlier detection (e.g., 3)
threshold = 3

# Find the indices of outliers based on the threshold
outlier_indices = np.where(z_scores > threshold)[0]

# Remove the outliers from the training data
X_train = X_train.drop(X_train.index[outlier_indices])
y_train = y_train.drop(y_train.index[outlier_indices])
```


```python
!pip install xgboost

```

    Requirement already satisfied: xgboost in c:\users\msn\appdata\local\anaconda3\lib\site-packages (1.7.6)
    Requirement already satisfied: scipy in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from xgboost) (1.10.0)
    Requirement already satisfied: numpy in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from xgboost) (1.23.5)
    


```python
from sklearn.model_selection import GridSearchCV, cross_val_score
from sklearn.linear_model import LogisticRegression
from sklearn.tree import DecisionTreeClassifier
from xgboost import XGBClassifier


# Estimator 1: Logistic Regression
lr_classifier = LogisticRegression(solver='liblinear', random_state=42)
lr_params = {'C': [0.1, 1.0, 10.0]}

# Estimator 2: Decision Tree Classifier
dt_classifier = DecisionTreeClassifier(random_state=42)
dt_params = {'max_depth': [None, 5, 10, 15]}

# Estimator 3: XGBoost Classifier
xgb_classifier = XGBClassifier(random_state=42)
xgb_params = {
    'n_estimators': [50, 100, 150],
    'max_depth': [3, 5, 7],
    'learning_rate': [0.1, 0.01, 0.001]
}

# Cross-validation untuk Logistic Regression
lr_grid_search = GridSearchCV(lr_classifier, lr_params, cv=5, scoring='accuracy')
lr_grid_search.fit(X_train, y_train)
print("Logistic Regression - Best Parameters:", lr_grid_search.best_params_)
print("Logistic Regression - Best Cross-validation Score:", lr_grid_search.best_score_)

# Cross-validation untuk Decision Tree Classifier
dt_grid_search = GridSearchCV(dt_classifier, dt_params, cv=5, scoring='accuracy')
dt_grid_search.fit(X_train, y_train)
print("Decision Tree Classifier - Best Parameters:", dt_grid_search.best_params_)
print("Decision Tree Classifier - Best Cross-validation Score:", dt_grid_search.best_score_)

# Cross-validation untuk XGBoost Classifier
xgb_grid_search = GridSearchCV(xgb_classifier, xgb_params, cv=5, scoring='accuracy')
xgb_grid_search.fit(X_train, y_train)
print("XGBoost Classifier - Best Parameters:", xgb_grid_search.best_params_)
print("XGBoost Classifier - Best Cross-validation Score:", xgb_grid_search.best_score_)
```

    Logistic Regression - Best Parameters: {'C': 1.0}
    Logistic Regression - Best Cross-validation Score: 0.8575072069186419
    Decision Tree Classifier - Best Parameters: {'max_depth': 5}
    Decision Tree Classifier - Best Cross-validation Score: 0.8207839525944907
    XGBoost Classifier - Best Parameters: {'learning_rate': 0.1, 'max_depth': 3, 'n_estimators': 150}
    XGBoost Classifier - Best Cross-validation Score: 0.871872998078155
    


```python
from sklearn.tree import DecisionTreeClassifier
from sklearn.model_selection import GridSearchCV
dtree = DecisionTreeClassifier(class_weight='balanced')
param_grid = {
    'max_depth': [3, 4, 5, 6, 7, 8],
    'min_samples_split': [2, 3, 4],
    'min_samples_leaf': [1, 2, 3, 4],
    'random_state': [0, 42]
}

# here performing a grid search with cross-validation to find the best the hyperparameters
grid_search = GridSearchCV(dtree, param_grid, cv=5)
grid_search.fit(X_train, y_train)

# Print the best hyperparameters
print(grid_search.best_params_)
```

    {'max_depth': 4, 'min_samples_leaf': 1, 'min_samples_split': 2, 'random_state': 0}
    


```python
from sklearn.tree import DecisionTreeClassifier
dtree = DecisionTreeClassifier(random_state=0, max_depth=8, min_samples_leaf=1, min_samples_split=2, class_weight='balanced')
dtree.fit(X_train, y_train)
```




<style>#sk-container-id-14 {color: black;background-color: white;}#sk-container-id-14 pre{padding: 0;}#sk-container-id-14 div.sk-toggleable {background-color: white;}#sk-container-id-14 label.sk-toggleable__label {cursor: pointer;display: block;width: 100%;margin-bottom: 0;padding: 0.3em;box-sizing: border-box;text-align: center;}#sk-container-id-14 label.sk-toggleable__label-arrow:before {content: "▸";float: left;margin-right: 0.25em;color: #696969;}#sk-container-id-14 label.sk-toggleable__label-arrow:hover:before {color: black;}#sk-container-id-14 div.sk-estimator:hover label.sk-toggleable__label-arrow:before {color: black;}#sk-container-id-14 div.sk-toggleable__content {max-height: 0;max-width: 0;overflow: hidden;text-align: left;background-color: #f0f8ff;}#sk-container-id-14 div.sk-toggleable__content pre {margin: 0.2em;color: black;border-radius: 0.25em;background-color: #f0f8ff;}#sk-container-id-14 input.sk-toggleable__control:checked~div.sk-toggleable__content {max-height: 200px;max-width: 100%;overflow: auto;}#sk-container-id-14 input.sk-toggleable__control:checked~label.sk-toggleable__label-arrow:before {content: "▾";}#sk-container-id-14 div.sk-estimator input.sk-toggleable__control:checked~label.sk-toggleable__label {background-color: #d4ebff;}#sk-container-id-14 div.sk-label input.sk-toggleable__control:checked~label.sk-toggleable__label {background-color: #d4ebff;}#sk-container-id-14 input.sk-hidden--visually {border: 0;clip: rect(1px 1px 1px 1px);clip: rect(1px, 1px, 1px, 1px);height: 1px;margin: -1px;overflow: hidden;padding: 0;position: absolute;width: 1px;}#sk-container-id-14 div.sk-estimator {font-family: monospace;background-color: #f0f8ff;border: 1px dotted black;border-radius: 0.25em;box-sizing: border-box;margin-bottom: 0.5em;}#sk-container-id-14 div.sk-estimator:hover {background-color: #d4ebff;}#sk-container-id-14 div.sk-parallel-item::after {content: "";width: 100%;border-bottom: 1px solid gray;flex-grow: 1;}#sk-container-id-14 div.sk-label:hover label.sk-toggleable__label {background-color: #d4ebff;}#sk-container-id-14 div.sk-serial::before {content: "";position: absolute;border-left: 1px solid gray;box-sizing: border-box;top: 0;bottom: 0;left: 50%;z-index: 0;}#sk-container-id-14 div.sk-serial {display: flex;flex-direction: column;align-items: center;background-color: white;padding-right: 0.2em;padding-left: 0.2em;position: relative;}#sk-container-id-14 div.sk-item {position: relative;z-index: 1;}#sk-container-id-14 div.sk-parallel {display: flex;align-items: stretch;justify-content: center;background-color: white;position: relative;}#sk-container-id-14 div.sk-item::before, #sk-container-id-14 div.sk-parallel-item::before {content: "";position: absolute;border-left: 1px solid gray;box-sizing: border-box;top: 0;bottom: 0;left: 50%;z-index: -1;}#sk-container-id-14 div.sk-parallel-item {display: flex;flex-direction: column;z-index: 1;position: relative;background-color: white;}#sk-container-id-14 div.sk-parallel-item:first-child::after {align-self: flex-end;width: 50%;}#sk-container-id-14 div.sk-parallel-item:last-child::after {align-self: flex-start;width: 50%;}#sk-container-id-14 div.sk-parallel-item:only-child::after {width: 0;}#sk-container-id-14 div.sk-dashed-wrapped {border: 1px dashed gray;margin: 0 0.4em 0.5em 0.4em;box-sizing: border-box;padding-bottom: 0.4em;background-color: white;}#sk-container-id-14 div.sk-label label {font-family: monospace;font-weight: bold;display: inline-block;line-height: 1.2em;}#sk-container-id-14 div.sk-label-container {text-align: center;}#sk-container-id-14 div.sk-container {/* jupyter's `normalize.less` sets `[hidden] { display: none; }` but bootstrap.min.css set `[hidden] { display: none !important; }` so we also need the `!important` here to be able to override the default hidden behavior on the sphinx rendered scikit-learn.org. See: https://github.com/scikit-learn/scikit-learn/issues/21755 */display: inline-block !important;position: relative;}#sk-container-id-14 div.sk-text-repr-fallback {display: none;}</style><div id="sk-container-id-14" class="sk-top-container"><div class="sk-text-repr-fallback"><pre>DecisionTreeClassifier(class_weight=&#x27;balanced&#x27;, max_depth=8, random_state=0)</pre><b>In a Jupyter environment, please rerun this cell to show the HTML representation or trust the notebook. <br />On GitHub, the HTML representation is unable to render, please try loading this page with nbviewer.org.</b></div><div class="sk-container" hidden><div class="sk-item"><div class="sk-estimator sk-toggleable"><input class="sk-toggleable__control sk-hidden--visually" id="sk-estimator-id-14" type="checkbox" checked><label for="sk-estimator-id-14" class="sk-toggleable__label sk-toggleable__label-arrow">DecisionTreeClassifier</label><div class="sk-toggleable__content"><pre>DecisionTreeClassifier(class_weight=&#x27;balanced&#x27;, max_depth=8, random_state=0)</pre></div></div></div></div></div>




```python
from sklearn.metrics import accuracy_score
y_pred = dtree.predict(X_test)
print("Accuracy Score :", round(accuracy_score(y_test, y_pred)*100 ,2), "%")
```

    Accuracy Score : 77.89 %
    


```python
from sklearn.metrics import accuracy_score, f1_score, precision_score, recall_score, jaccard_score, log_loss
print('F-1 Score : ',(f1_score(y_test, y_pred, average='micro')))
print('Precision Score : ',(precision_score(y_test, y_pred, average='micro')))
print('Recall Score : ',(recall_score(y_test, y_pred, average='micro')))
print('Jaccard Score : ',(jaccard_score(y_test, y_pred, average='micro')))
print('Log Loss : ',(log_loss(y_test, y_pred)))
```

    F-1 Score :  0.7789115646258504
    Precision Score :  0.7789115646258503
    Recall Score :  0.7789115646258503
    Jaccard Score :  0.637883008356546
    Log Loss :  7.968834932968078
    


```python
imp_df = pd.DataFrame({
    "Feature Name": X_train.columns,
    "Importance": dtree.feature_importances_
})
fi = imp_df.sort_values(by="Importance", ascending=False)

fi2 = fi.head(10)
plt.figure(figsize=(10,8))
sns.barplot(data=fi2, x='Importance', y='Feature Name')
plt.title('Top 10 Feature Importance Each Attributes (Decision Tree)', fontsize=18)
plt.xlabel ('Importance', fontsize=16)
plt.ylabel ('Feature Name', fontsize=16)
plt.show()
```


    
![png](output_31_0.png)
    



```python
!pip install shap

```

    Requirement already satisfied: shap in c:\users\msn\appdata\local\anaconda3\lib\site-packages (0.42.1)
    Requirement already satisfied: numba in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from shap) (0.56.4)
    Requirement already satisfied: scipy in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from shap) (1.10.0)
    Requirement already satisfied: scikit-learn in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from shap) (1.2.1)
    Requirement already satisfied: cloudpickle in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from shap) (2.0.0)
    Requirement already satisfied: pandas in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from shap) (1.5.3)
    Requirement already satisfied: packaging>20.9 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from shap) (22.0)
    Requirement already satisfied: tqdm>=4.27.0 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from shap) (4.64.1)
    Requirement already satisfied: numpy in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from shap) (1.23.5)
    Requirement already satisfied: slicer==0.0.7 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from shap) (0.0.7)
    Requirement already satisfied: colorama in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from tqdm>=4.27.0->shap) (0.4.6)
    Requirement already satisfied: setuptools in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from numba->shap) (65.6.3)
    Requirement already satisfied: llvmlite<0.40,>=0.39.0dev0 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from numba->shap) (0.39.1)
    Requirement already satisfied: pytz>=2020.1 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from pandas->shap) (2022.7)
    Requirement already satisfied: python-dateutil>=2.8.1 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from pandas->shap) (2.8.2)
    Requirement already satisfied: threadpoolctl>=2.0.0 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from scikit-learn->shap) (2.2.0)
    Requirement already satisfied: joblib>=1.1.1 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from scikit-learn->shap) (1.1.1)
    Requirement already satisfied: six>=1.5 in c:\users\msn\appdata\local\anaconda3\lib\site-packages (from python-dateutil>=2.8.1->pandas->shap) (1.16.0)
    


```python
import shap
explainer = shap.TreeExplainer(dtree)
shap_values = explainer.shap_values(X_test)
shap.summary_plot(shap_values, X_test)
```


    
![png](output_33_0.png)
    



```python
# compute SHAP values
explainer = shap.TreeExplainer(dtree)
shap_values = explainer.shap_values(X_test)
shap.summary_plot(shap_values[1], X_test.values, feature_names = X_test.columns)
```

    No data for colormapping provided via 'c'. Parameters 'vmin', 'vmax' will be ignored
    


    
![png](output_34_1.png)
    



```python
from sklearn.metrics import confusion_matrix
cm = confusion_matrix(y_test, y_pred)
plt.figure(figsize=(5,5))
sns.heatmap(data=cm,linewidths=.5, annot=True,  cmap = 'Blues')
plt.ylabel('Actual label')
plt.xlabel('Predicted label')
all_sample_title = 'Accuracy Score for Decision Tree: {0}'.format(dtree.score(X_test, y_test))
plt.title(all_sample_title, size = 15)
```




    Text(0.5, 1.0, 'Accuracy Score for Decision Tree: 0.7789115646258503')




    
![png](output_35_1.png)
    



```python
from sklearn.metrics import roc_curve, roc_auc_score
y_pred_proba = dtree.predict_proba(X_test)[:][:,1]

df_actual_predicted = pd.concat([pd.DataFrame(np.array(y_test), columns=['y_actual']), pd.DataFrame(y_pred_proba, columns=['y_pred_proba'])], axis=1)
df_actual_predicted.index = y_test.index

fpr, tpr, tr = roc_curve(df_actual_predicted['y_actual'], df_actual_predicted['y_pred_proba'])
auc = roc_auc_score(df_actual_predicted['y_actual'], df_actual_predicted['y_pred_proba'])

plt.plot(fpr, tpr, label='AUC = %0.4f' %auc)
plt.plot(fpr, fpr, linestyle = '--', color='k')
plt.xlabel('False Positive Rate')
plt.ylabel('True Positive Rate')
plt.title('ROC Curve', size = 15)
plt.legend()
```




    <matplotlib.legend.Legend at 0x1da04d1f730>




    
![png](output_36_1.png)
    



```python
from sklearn.ensemble import RandomForestClassifier
from sklearn.model_selection import GridSearchCV
rfc = RandomForestClassifier(class_weight='balanced')
param_grid = {
    'n_estimators': [100, 200],
    'max_depth': [None, 5, 10],
    'max_features': ['sqrt', 'log2', None],
    'random_state': [0, 42]
}

grid_search = GridSearchCV(rfc, param_grid, cv=5)
grid_search.fit(X_train, y_train)

print(grid_search.best_params_)
```

    {'max_depth': 10, 'max_features': None, 'n_estimators': 100, 'random_state': 42}
    


```python
from sklearn.ensemble import RandomForestClassifier
rfc = RandomForestClassifier(random_state=42, max_depth=None, max_features='sqrt', n_estimators=100, class_weight='balanced')
rfc.fit(X_train, y_train)
```




<style>#sk-container-id-16 {color: black;background-color: white;}#sk-container-id-16 pre{padding: 0;}#sk-container-id-16 div.sk-toggleable {background-color: white;}#sk-container-id-16 label.sk-toggleable__label {cursor: pointer;display: block;width: 100%;margin-bottom: 0;padding: 0.3em;box-sizing: border-box;text-align: center;}#sk-container-id-16 label.sk-toggleable__label-arrow:before {content: "▸";float: left;margin-right: 0.25em;color: #696969;}#sk-container-id-16 label.sk-toggleable__label-arrow:hover:before {color: black;}#sk-container-id-16 div.sk-estimator:hover label.sk-toggleable__label-arrow:before {color: black;}#sk-container-id-16 div.sk-toggleable__content {max-height: 0;max-width: 0;overflow: hidden;text-align: left;background-color: #f0f8ff;}#sk-container-id-16 div.sk-toggleable__content pre {margin: 0.2em;color: black;border-radius: 0.25em;background-color: #f0f8ff;}#sk-container-id-16 input.sk-toggleable__control:checked~div.sk-toggleable__content {max-height: 200px;max-width: 100%;overflow: auto;}#sk-container-id-16 input.sk-toggleable__control:checked~label.sk-toggleable__label-arrow:before {content: "▾";}#sk-container-id-16 div.sk-estimator input.sk-toggleable__control:checked~label.sk-toggleable__label {background-color: #d4ebff;}#sk-container-id-16 div.sk-label input.sk-toggleable__control:checked~label.sk-toggleable__label {background-color: #d4ebff;}#sk-container-id-16 input.sk-hidden--visually {border: 0;clip: rect(1px 1px 1px 1px);clip: rect(1px, 1px, 1px, 1px);height: 1px;margin: -1px;overflow: hidden;padding: 0;position: absolute;width: 1px;}#sk-container-id-16 div.sk-estimator {font-family: monospace;background-color: #f0f8ff;border: 1px dotted black;border-radius: 0.25em;box-sizing: border-box;margin-bottom: 0.5em;}#sk-container-id-16 div.sk-estimator:hover {background-color: #d4ebff;}#sk-container-id-16 div.sk-parallel-item::after {content: "";width: 100%;border-bottom: 1px solid gray;flex-grow: 1;}#sk-container-id-16 div.sk-label:hover label.sk-toggleable__label {background-color: #d4ebff;}#sk-container-id-16 div.sk-serial::before {content: "";position: absolute;border-left: 1px solid gray;box-sizing: border-box;top: 0;bottom: 0;left: 50%;z-index: 0;}#sk-container-id-16 div.sk-serial {display: flex;flex-direction: column;align-items: center;background-color: white;padding-right: 0.2em;padding-left: 0.2em;position: relative;}#sk-container-id-16 div.sk-item {position: relative;z-index: 1;}#sk-container-id-16 div.sk-parallel {display: flex;align-items: stretch;justify-content: center;background-color: white;position: relative;}#sk-container-id-16 div.sk-item::before, #sk-container-id-16 div.sk-parallel-item::before {content: "";position: absolute;border-left: 1px solid gray;box-sizing: border-box;top: 0;bottom: 0;left: 50%;z-index: -1;}#sk-container-id-16 div.sk-parallel-item {display: flex;flex-direction: column;z-index: 1;position: relative;background-color: white;}#sk-container-id-16 div.sk-parallel-item:first-child::after {align-self: flex-end;width: 50%;}#sk-container-id-16 div.sk-parallel-item:last-child::after {align-self: flex-start;width: 50%;}#sk-container-id-16 div.sk-parallel-item:only-child::after {width: 0;}#sk-container-id-16 div.sk-dashed-wrapped {border: 1px dashed gray;margin: 0 0.4em 0.5em 0.4em;box-sizing: border-box;padding-bottom: 0.4em;background-color: white;}#sk-container-id-16 div.sk-label label {font-family: monospace;font-weight: bold;display: inline-block;line-height: 1.2em;}#sk-container-id-16 div.sk-label-container {text-align: center;}#sk-container-id-16 div.sk-container {/* jupyter's `normalize.less` sets `[hidden] { display: none; }` but bootstrap.min.css set `[hidden] { display: none !important; }` so we also need the `!important` here to be able to override the default hidden behavior on the sphinx rendered scikit-learn.org. See: https://github.com/scikit-learn/scikit-learn/issues/21755 */display: inline-block !important;position: relative;}#sk-container-id-16 div.sk-text-repr-fallback {display: none;}</style><div id="sk-container-id-16" class="sk-top-container"><div class="sk-text-repr-fallback"><pre>RandomForestClassifier(class_weight=&#x27;balanced&#x27;, random_state=42)</pre><b>In a Jupyter environment, please rerun this cell to show the HTML representation or trust the notebook. <br />On GitHub, the HTML representation is unable to render, please try loading this page with nbviewer.org.</b></div><div class="sk-container" hidden><div class="sk-item"><div class="sk-estimator sk-toggleable"><input class="sk-toggleable__control sk-hidden--visually" id="sk-estimator-id-16" type="checkbox" checked><label for="sk-estimator-id-16" class="sk-toggleable__label sk-toggleable__label-arrow">RandomForestClassifier</label><div class="sk-toggleable__content"><pre>RandomForestClassifier(class_weight=&#x27;balanced&#x27;, random_state=42)</pre></div></div></div></div></div>




```python
y_pred = rfc.predict(X_test)
print("Accuracy Score :", round(accuracy_score(y_test, y_pred)*100 ,2), "%")
```

    Accuracy Score : 85.03 %
    


```python
from sklearn.metrics import accuracy_score, f1_score, precision_score, recall_score, jaccard_score, log_loss
print('F1 Score : ',(f1_score(y_test, y_pred, average='micro')))
print('Precision Score : ',(precision_score(y_test, y_pred, average='micro')))
print('Recall Score : ',(recall_score(y_test, y_pred, average='micro')))
print('Jaccard Score : ',(jaccard_score(y_test, y_pred, average='micro')))
print('Log Loss : ',(log_loss(y_test, y_pred)))
```

    F1 Score :  0.8503401360544217
    Precision Score :  0.8503401360544217
    Recall Score :  0.8503401360544217
    Jaccard Score :  0.7396449704142012
    Log Loss :  5.394288262316852
    


```python
imp_df = pd.DataFrame({
    "Feature Name": X_train.columns,
    "Importance": rfc.feature_importances_
})
fi = imp_df.sort_values(by="Importance", ascending=False)

fi2 = fi.head(10)
plt.figure(figsize=(10,8))
sns.barplot(data=fi2, x='Importance', y='Feature Name')
plt.title('Top 10 Feature Importance Each Attributes (Random Forest)', fontsize=18)
plt.xlabel ('Importance', fontsize=16)
plt.ylabel ('Feature Name', fontsize=16)
plt.show()
```


    
![png](output_41_0.png)
    



```python
import shap
explainer = shap.TreeExplainer(rfc)
shap_values = explainer.shap_values(X_test)
shap.summary_plot(shap_values, X_test)
```


    
![png](output_42_0.png)
    



```python

explainer = shap.TreeExplainer(rfc)
shap_values = explainer.shap_values(X_test)
shap.summary_plot(shap_values[1], X_test.values, feature_names = X_test.columns)
```


```python
from sklearn.metrics import confusion_matrix
cm = confusion_matrix(y_test, y_pred)
plt.figure(figsize=(5,5))
sns.heatmap(data=cm,linewidths=.5, annot=True,  cmap = 'Blues')
plt.ylabel('Actual label')
plt.xlabel('Predicted label')
all_sample_title = 'Accuracy Score for Random Forest: {0}'.format(rfc.score(X_test, y_test))
plt.title(all_sample_title, size = 15)
```


```python
from sklearn.metrics import roc_curve, roc_auc_score
y_pred_proba = rfc.predict_proba(X_test)[:][:,1]

df_actual_predicted = pd.concat([pd.DataFrame(np.array(y_test), columns=['y_actual']), pd.DataFrame(y_pred_proba, columns=['y_pred_proba'])], axis=1)
df_actual_predicted.index = y_test.index

fpr, tpr, tr = roc_curve(df_actual_predicted['y_actual'], df_actual_predicted['y_pred_proba'])
auc = roc_auc_score(df_actual_predicted['y_actual'], df_actual_predicted['y_pred_proba'])

plt.plot(fpr, tpr, label='AUC = %0.4f' %auc)
plt.plot(fpr, fpr, linestyle = '--', color='k')
plt.xlabel('False Positive Rate')
plt.ylabel('True Positive Rate')
plt.title('ROC Curve', size = 15)
plt.legend()
```


```python
from sklearn.model_selection import GridSearchCV
from xgboost import XGBClassifier

# Create an XGBoost classifier
xgb = XGBClassifier()

# Define the parameter grid for grid search
param_grid = {
    'n_estimators': [100, 200],
    'max_depth': [3, 5, 7],
    'learning_rate': [0.1, 0.01, 0.001],
    'gamma': [0, 0.1, 0.2]
}

# Perform a grid search with cross-validation to find the best hyperparameters
grid_search = GridSearchCV(xgb, param_grid, cv=5)
grid_search.fit(X_train, y_train)

# Print the best hyperparameters
print(grid_search.best_params_)
```


```python
from xgboost import XGBClassifier
xgb = XGBClassifier(gamma=0.2, learning_rate=0.1, max_depth=7, n_estimators=200)
xgb.fit(X_train, y_train)
```


```python
from sklearn.metrics import accuracy_score
y_pred = xgb.predict(X_test)
print("Accuracy Score :", round(accuracy_score(y_test, y_pred)*100 ,2), "%")
```


```python
from sklearn.metrics import accuracy_score, f1_score, precision_score, recall_score, jaccard_score, log_loss
print('F-1 Score : ',(f1_score(y_test, y_pred, average='micro')))
print('Precision Score : ',(precision_score(y_test, y_pred, average='micro')))
print('Recall Score : ',(recall_score(y_test, y_pred, average='micro')))
print('Jaccard Score : ',(jaccard_score(y_test, y_pred, average='micro')))
print('Log Loss : ',(log_loss(y_test, y_pred)))
```


```python
import shap
explainer = shap.TreeExplainer(xgb)
shap_values = explainer.shap_values(X_test)
shap.summary_plot(shap_values, X_test)
```


```python
from sklearn.metrics import confusion_matrix
cm = confusion_matrix(y_test, y_pred)
plt.figure(figsize=(5,5))
sns.heatmap(data=cm,linewidths=.5, annot=True,  cmap = 'Blues')
plt.ylabel('Actual label')
plt.xlabel('Predicted label')
all_sample_title = 'Accuracy Score for XGBoost: {0}'.format(xgb.score(X_test, y_test))
plt.title(all_sample_title, size = 15)
```


```python
from sklearn.metrics import roc_curve, roc_auc_score
y_pred_proba = xgb.predict_proba(X_test)[:][:,1]

df_actual_predicted = pd.concat([pd.DataFrame(np.array(y_test), columns=['y_actual']), pd.DataFrame(y_pred_proba, columns=['y_pred_proba'])], axis=1)
df_actual_predicted.index = y_test.index

fpr, tpr, tr = roc_curve(df_actual_predicted['y_actual'], df_actual_predicted['y_pred_proba'])
auc = roc_auc_score(df_actual_predicted['y_actual'], df_actual_predicted['y_pred_proba'])

plt.plot(fpr, tpr, label='AUC = %0.4f' %auc)
plt.plot(fpr, fpr, linestyle = '--', color='k')
plt.xlabel('False Positive Rate')
plt.ylabel('True Positive Rate')
plt.title('ROC Curve', size = 15)
plt.legend()
```


```python
df1 = pd.read_csv('employee.csv')
df1.head()
```


```python
df1.drop(columns=['Unnamed: 0','EmployeeNumber', 'StandardHours','Over18', 'PerformanceRating'], inplace=True)
```


```python
from sklearn import preprocessing

# Loop over each column in the DataFrame where dtype is 'object'
for col in df1.select_dtypes(include=['object']).columns:

    # Initialize a LabelEncoder object
    label_encoder = preprocessing.LabelEncoder()

    # Fit the encoder to the unique values in the column
    label_encoder.fit(df1[col].unique())

    # Transform the column using the encoder
    df1[col] = label_encoder.transform(df1[col])

    # Print the column name and the unique encoded values
    print(f"{col}: {df1[col].unique()}")
```


```python
X = df1.drop('MonthlyIncome', axis=1)
y = df1['MonthlyIncome']
```


```python
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=0)
```


```python
from scipy import stats

# Define the columns for which you want to remove outliers
selected_columns = ['StockOptionLevel', 'TotalWorkingYears', 'TrainingTimesLastYear', 'YearsAtCompany',
                    'YearsInCurrentRole', 'YearsSinceLastPromotion', 'YearsWithCurrManager']

# Calculate the Z-scores for the selected columns in the training data
z_scores = np.abs(stats.zscore(X_train[selected_columns]))

# Set a threshold value for outlier detection (e.g., 3)
threshold = 3

# Find the indices of outliers based on the threshold
outlier_indices = np.where(z_scores > threshold)[0]

# Remove the outliers from the training data
X_train = X_train.drop(X_train.index[outlier_indices])
y_train = y_train.drop(y_train.index[outlier_indices])
```


```python
from sklearn.model_selection import GridSearchCV, cross_val_score
from sklearn.linear_model import LinearRegression
from sklearn.preprocessing import PolynomialFeatures
from sklearn.tree import DecisionTreeRegressor
from sklearn.ensemble import RandomForestRegressor
from xgboost import XGBRegressor
from sklearn.metrics import mean_squared_error

# Regressor 1: Linear/Polynomial Regression
linear_regressor = LinearRegression()
poly_regressor = LinearRegression()


polynomial_features = PolynomialFeatures(degree=2)
X_train_poly = polynomial_features.fit_transform(X_train)
X_test_poly = polynomial_features.transform(X_test)

# Cross-validation Linear Regression
linear_scores = cross_val_score(linear_regressor, X_train, y_train, cv=5, scoring='neg_mean_squared_error')
linear_rmse = np.sqrt(-linear_scores.mean())

# Cross-validation Polynomial Regression
poly_scores = cross_val_score(poly_regressor, X_train_poly, y_train, cv=5, scoring='neg_mean_squared_error')
poly_rmse = np.sqrt(-poly_scores.mean())

print("Linear Regression - Cross-validation RMSE:", linear_rmse)
print("Polynomial Regression - Cross-validation RMSE:", poly_rmse)

# Regressor 2: Decision Tree/Random Forest/XGBoost Regressor
dt_regressor = DecisionTreeRegressor(random_state=42)
rf_regressor = RandomForestRegressor(random_state=42)
xgb_regressor = XGBRegressor(random_state=42)

# Hyperparameter grid for Decision Tree Regressor
dt_params = {
    'max_depth': [2, 4, 6, 8, None],
    'min_samples_split': [2, 4, 6, 8],
    'min_samples_leaf': [1, 2, 3, 4],
    'max_features': ['auto', 'sqrt', 'log2']
}

# Hyperparameter grid for Random Forest Regressor
rf_params = {
    'n_estimators': [50, 100, 150],
    'max_depth': [None, 5, 10],
    'min_samples_split': [2, 5, 10]
}

# Hyperparameter grid for XGBoost Regressor
xgb_params = {
    'n_estimators': [50, 100, 150],
    'max_depth': [3, 5, 7],
    'learning_rate': [0.1, 0.01, 0.001]
}

# Hyperparameter grid for Polynomial Regression
poly_params = {
    'fit_intercept': [True, False],
    'normalize': [True, False]
}

# Hyperparameter grid for Linear Regression
linear_params = {
    'fit_intercept': [True, False],
    'normalize': [True, False]
}

# GridSearchCV for Decision Tree Regressor
dt_grid_search = GridSearchCV(dt_regressor, dt_params, cv=5, scoring='neg_mean_squared_error')
dt_grid_search.fit(X_train, y_train)
print("Decision Tree Regressor - Best Parameters:", dt_grid_search.best_params_)
print("Decision Tree Regressor - Best Cross-validation RMSE:", np.sqrt(-dt_grid_search.best_score_))

# GridSearchCV for Random Forest Regressor
rf_grid_search = GridSearchCV(rf_regressor, rf_params, cv=5, scoring='neg_mean_squared_error')
rf_grid_search.fit(X_train, y_train)
print("Random Forest Regressor - Best Parameters:", rf_grid_search.best_params_)
print("Random Forest Regressor - Best Cross-validation RMSE:", np.sqrt(-rf_grid_search.best_score_))

# GridSearchCV for XGBoost Regressor
xgb_grid_search = GridSearchCV(xgb_regressor, xgb_params, cv=5, scoring='neg_mean_squared_error')
xgb_grid_search.fit(X_train, y_train)
print("XGBoost Regressor - Best Parameters:", xgb_grid_search.best_params_)
print("XGBoost Regressor - Best Cross-validation RMSE:", np.sqrt(-xgb_grid_search.best_score_))

# GridSearchCV for Polynomial Regression
poly_grid_search = GridSearchCV(poly_regressor, poly_params, cv=5, scoring='neg_mean_squared_error')
poly_grid_search.fit(X_train_poly, y_train)
print("Polynomial Regression - Best Parameters:", poly_grid_search.best_params_)
print("Polynomial Regression - Best Cross-validation RMSE:", np.sqrt(-poly_grid_search.best_score_))

# GridSearchCV for Linear Regression
linear_grid_search = GridSearchCV(linear_regressor, linear_params, cv=5, scoring='neg_mean_squared_error')
linear_grid_search.fit(X_train, y_train)
print("Linear Regression - Best Parameters:", linear_grid_search.best_params_)
print("Linear Regression - Best Cross-validation RMSE:", np.sqrt(-linear_grid_search.best_score_))

```


```python
from sklearn.tree import DecisionTreeRegressor
dtree = DecisionTreeRegressor(random_state=0, max_depth=None, max_features='auto', min_samples_leaf=1, min_samples_split=2)
dtree.fit(X_train, y_train)
```


```python
from sklearn import metrics
import math
y_pred = dtree.predict(X_test)
mae = metrics.mean_absolute_error(y_test, y_pred)
mse = metrics.mean_squared_error(y_test, y_pred)
r2 = metrics.r2_score(y_test, y_pred)
rmse = math.sqrt(mse)

print('MAE is {}'.format(mae))
print('MSE is {}'.format(mse))
print('R2 score is {}'.format(r2))
print('RMSE score is {}'.format(rmse))
```


```python
imp_df = pd.DataFrame({
    "Feature Name": X_train.columns,
    "Importance": dtree.feature_importances_
})
fi = imp_df.sort_values(by="Importance", ascending=False)

fi2 = fi.head(10)
plt.figure(figsize=(10,8))
sns.barplot(data=fi2, x='Importance', y='Feature Name')
plt.title('Feature Importance Each Attributes (Decision Tree Regressor)', fontsize=18)
plt.xlabel ('Importance', fontsize=16)
plt.ylabel ('Feature Name', fontsize=16)
plt.show()
```


```python
import shap
explainer = shap.TreeExplainer(dtree)
shap_values = explainer.shap_values(X_test)
shap.summary_plot(shap_values, X_test)
```


```python
explainer = shap.Explainer(dtree, X_test)
shap_values = explainer(X_test)
shap.plots.waterfall(shap_values[0])
```


```python
from sklearn.ensemble import RandomForestRegressor
rf = RandomForestRegressor(random_state=0, max_depth=None, min_samples_split=2, n_estimators= 100)
rf.fit(X_train, y_train)
```


```python
from sklearn import metrics
from sklearn.metrics import mean_absolute_percentage_error
import math
y_pred = rf.predict(X_test)
mae = metrics.mean_absolute_error(y_test, y_pred)
mape = mean_absolute_percentage_error(y_test, y_pred)
mse = metrics.mean_squared_error(y_test, y_pred)
r2 = metrics.r2_score(y_test, y_pred)
rmse = math.sqrt(mse)

print('MAE is {}'.format(mae))
print('MAPE is {}'.format(mape))
print('MSE is {}'.format(mse))
print('R2 score is {}'.format(r2))
print('RMSE score is {}'.format(rmse))
```


```python
imp_df = pd.DataFrame({
    "Feature Name": X_train.columns,
    "Importance": dtree.feature_importances_
})
fi = imp_df.sort_values(by="Importance", ascending=False)

fi2 = fi.head(10)
plt.figure(figsize=(10,8))
sns.barplot(data=fi2, x='Importance', y='Feature Name')
plt.title('Feature Importance Each Attributes (Random Forest Regressor)', fontsize=18)
plt.xlabel ('Importance', fontsize=16)
plt.ylabel ('Feature Name', fontsize=16)
plt.show()
```


```python
import shap
explainer = shap.TreeExplainer(rf)
shap_values = explainer.shap_values(X_test)
shap.summary_plot(shap_values, X_test)
```


```python
explainer = shap.Explainer(rf, X_test, check_additivity=False)
shap_values = explainer(X_test, check_additivity=False)
shap.plots.waterfall(shap_values[0])
```


```python
from xgboost import XGBRegressor
xgb_regressor = XGBRegressor(learning_rate= 0.1, max_depth= 7, n_estimators= 150)
xgb_regressor.fit(X_train, y_train)
```


```python
from sklearn import metrics
from sklearn.metrics import mean_absolute_percentage_error
import math
y_pred = xgb_regressor.predict(X_test)
mae = metrics.mean_absolute_error(y_test, y_pred)
mape = mean_absolute_percentage_error(y_test, y_pred)
mse = metrics.mean_squared_error(y_test, y_pred)
r2 = metrics.r2_score(y_test, y_pred)
rmse = math.sqrt(mse)

print('MAE is {}'.format(mae))
print('MAPE is {}'.format(mape))
print('MSE is {}'.format(mse))
print('R2 score is {}'.format(r2))
print('RMSE score is {}'.format(rmse))
```


```python
import shap
explainer = shap.TreeExplainer(xgb_regressor)
shap_values = explainer.shap_values(X_test)
shap.summary_plot(shap_values, X_test)
```


```python
explainer = shap.Explainer(xgb_regressor, X_test, check_additivity=False)
shap_values = explainer(X_test, check_additivity=False)
shap.plots.waterfall(shap_values[0])
```


```python
import numpy as np
from sklearn.linear_model import LinearRegression

# Train linear regression model
linreg = LinearRegression(fit_intercept=True)
linreg.fit(X_train, y_train)

```


```python
from sklearn import metrics
from sklearn.metrics import mean_absolute_percentage_error
import math
y_pred = linreg.predict(X_test)
mae = metrics.mean_absolute_error(y_test, y_pred)
mape = mean_absolute_percentage_error(y_test, y_pred)
mse = metrics.mean_squared_error(y_test, y_pred)
r2 = metrics.r2_score(y_test, y_pred)
rmse = math.sqrt(mse)

print('MAE is {}'.format(mae))
print('MAPE is {}'.format(mape))
print('MSE is {}'.format(mse))
print('R2 score is {}'.format(r2))
print('RMSE score is {}'.format(rmse))
```


```python
imp_df = pd.DataFrame({
    "Feature Name": X_train.columns,
    "Importance": np.abs(linreg.coef_)
})

# Sort by importance (absolute value of coefficients)
fi = imp_df.sort_values(by="Importance", ascending=False)

# Select the top 10 features
fi2 = fi.head(10)

# Plot the feature importance
plt.figure(figsize=(10, 8))
sns.barplot(data=fi2, x='Importance', y='Feature Name')
plt.title('Feature Importance Each Attribute (Linear Regression)', fontsize=18)
plt.xlabel('Importance', fontsize=16)
plt.ylabel('Feature Name', fontsize=16)
plt.show()
```


```python
from sklearn.linear_model import LinearRegression
from sklearn.tree import DecisionTreeRegressor
from sklearn.ensemble import RandomForestRegressor
from xgboost import XGBRegressor
from sklearn.metrics import mean_squared_error, mean_absolute_error
from sklearn.metrics import mean_absolute_percentage_error as MAPE

# Regressor 1: Linear Regression
linear_regressor = LinearRegression(fit_intercept=True)
linear_regressor.fit(X_train, y_train)

y_train_pred_linear = linear_regressor.predict(X_train)
y_test_pred_linear = linear_regressor.predict(X_test)

# Calculate metrics for Linear Regression
linear_r2_train = linear_regressor.score(X_train, y_train)
linear_r2_test = linear_regressor.score(X_test, y_test)
linear_mse_train = mean_squared_error(y_train, y_train_pred_linear)
linear_mse_test = mean_squared_error(y_test, y_test_pred_linear)
linear_rmse_train = np.sqrt(linear_mse_train)
linear_rmse_test = np.sqrt(linear_mse_test)
linear_mae_train = mean_absolute_error(y_train, y_train_pred_linear)
linear_mae_test = mean_absolute_error(y_test, y_test_pred_linear)
linear_mape_train = MAPE(y_train, y_train_pred_linear)
linear_mape_test = MAPE(y_test, y_test_pred_linear)

# Regressor 2: Decision Tree Regressor
dt_regressor = DecisionTreeRegressor(random_state=0, max_depth=None, max_features='auto', min_samples_leaf=1, min_samples_split=2)
dt_regressor.fit(X_train, y_train)

y_train_pred_dt = dt_regressor.predict(X_train)
y_test_pred_dt = dt_regressor.predict(X_test)

# Calculate metrics for Decision Tree Regressor
dt_r2_train = dt_regressor.score(X_train, y_train)
dt_r2_test = dt_regressor.score(X_test, y_test)
dt_mse_train = mean_squared_error(y_train, y_train_pred_dt)
dt_mse_test = mean_squared_error(y_test, y_test_pred_dt)
dt_rmse_train = np.sqrt(dt_mse_train)
dt_rmse_test = np.sqrt(dt_mse_test)
dt_mae_train = mean_absolute_error(y_train, y_train_pred_dt)
dt_mae_test = mean_absolute_error(y_test, y_test_pred_dt)
dt_mape_train = MAPE(y_train, y_train_pred_dt)
dt_mape_test = MAPE(y_test, y_test_pred_dt)

# Regressor 3: Random Forest Regressor
rf_regressor = RandomForestRegressor(random_state=0, max_depth=None, min_samples_split=2, n_estimators= 100)
rf_regressor.fit(X_train, y_train)

y_train_pred_rf = rf_regressor.predict(X_train)
y_test_pred_rf = rf_regressor.predict(X_test)

# Calculate metrics for Random Forest Regressor
rf_r2_train = rf_regressor.score(X_train, y_train)
rf_r2_test = rf_regressor.score(X_test, y_test)
rf_mse_train = mean_squared_error(y_train, y_train_pred_rf)
rf_mse_test = mean_squared_error(y_test, y_test_pred_rf)
rf_rmse_train = np.sqrt(rf_mse_train)
rf_rmse_test = np.sqrt(rf_mse_test)
rf_mae_train = mean_absolute_error(y_train, y_train_pred_rf)
rf_mae_test = mean_absolute_error(y_test, y_test_pred_rf)
rf_mape_train = MAPE(y_train, y_train_pred_rf)
rf_mape_test = MAPE(y_test, y_test_pred_rf)

# Regressor 4: XGBoost Regressor
xgb_regressor = XGBRegressor(learning_rate= 0.1, max_depth= 7, n_estimators= 150)
xgb_regressor.fit(X_train, y_train)

y_train_pred_xgb = xgb_regressor.predict(X_train)
y_test_pred_xgb = xgb_regressor.predict(X_test)

# Calculate metrics for XGBoost Regressor
xgb_r2_train = xgb_regressor.score(X_train, y_train)
xgb_r2_test = xgb_regressor.score(X_test, y_test)
xgb_mse_train = mean_squared_error(y_train, y_train_pred_xgb)
xgb_mse_test = mean_squared_error(y_test, y_test_pred_xgb)
xgb_rmse_train = np.sqrt(xgb_mse_train)
xgb_rmse_test = np.sqrt(xgb_mse_test)
xgb_mae_train = mean_absolute_error(y_train, y_train_pred_xgb)
xgb_mae_test = mean_absolute_error(y_test, y_test_pred_xgb)
xgb_mape_train = MAPE(y_train, y_train_pred_xgb)
xgb_mape_test = MAPE(y_test, y_test_pred_xgb)

# Create a dataframe to compare the performance of the regressors
metrics_data = {
    'Regressor': ['Linear Regression', 'Decision Tree Regressor', 'Random Forest Regressor', 'XGBoost Regressor'],
    'R2 (Train)': [linear_r2_train, dt_r2_train, rf_r2_train, xgb_r2_train],
    'R2 (Test)': [linear_r2_test, dt_r2_test, rf_r2_test, xgb_r2_test],
    'MSE (Train)': [linear_mse_train, dt_mse_train, rf_mse_train, xgb_mse_train],
    'MSE (Test)': [linear_mse_test, dt_mse_test, rf_mse_test, xgb_mse_test],
    'RMSE (Train)': [linear_rmse_train, dt_rmse_train, rf_rmse_train, xgb_rmse_train],
    'RMSE (Test)': [linear_rmse_test, dt_rmse_test, rf_rmse_test, xgb_rmse_test],
    'MAE (Train)': [linear_mae_train, dt_mae_train, rf_mae_train, xgb_mae_train],
    'MAE (Test)': [linear_mae_test, dt_mae_test, rf_mae_test, xgb_mae_test],
    'MAPE (Train)': [linear_mape_train, dt_mape_train, rf_mape_train, xgb_mape_train],
    'MAPE (Test)': [linear_mape_test, dt_mape_test, rf_mape_test, xgb_mape_test]
}

metrics_df = pd.DataFrame(metrics_data)
metrics_df
```


```python

```


```python
import pandas as pd

# Read the CSV file into DataFrame
df2 = pd.read_csv('employee.csv')

# Print the column names and the first few rows of the DataFrame
print("Column Names:", df2.columns)
print(df2.head())

# Drop specified columns if they exist
columns_to_drop = ['EmployeeNumber', 'StandardHours', 'Over18', 'PerformanceRating']
df2.drop(columns=columns_to_drop, inplace=True)

```


```python
from sklearn.cluster import KMeans
from sklearn.metrics import silhouette_score

# Function to find optimal k using the Elbow Method
def find_optimal_k_elbow(X, max_k):
    inertias = []
    for k in range(1, max_k + 1):
        kmeans = KMeans(n_clusters=k, random_state=42)
        kmeans.fit(X)
        inertias.append(kmeans.inertia_)

    # Plot Elbow graph
    plt.figure(figsize=(8, 6))
    plt.plot(range(1, max_k + 1), inertias, marker='o')
    plt.xlabel('Number of clusters (k)')
    plt.ylabel('Inertia')
    plt.title('Elbow Method')
    plt.show()

# Function to find optimal k using the Silhouette Score
def find_optimal_k_silhouette(X, max_k):
    silhouette_scores = []
    for k in range(2, max_k + 1):
        kmeans = KMeans(n_clusters=k, random_state=42)
        kmeans.fit(X)
        labels = kmeans.labels_
        silhouette_scores.append(silhouette_score(X, labels))

    # Plot Silhouette Score graph
    plt.figure(figsize=(8, 6))
    plt.plot(range(2, max_k + 1), silhouette_scores, marker='o')
    plt.xlabel('Number of clusters (k)')
    plt.ylabel('Silhouette Score')
    plt.title('Silhouette Score')
    plt.show()

selected_columns = ['MonthlyIncome', 'Age', 'DailyRate']
X = df2[selected_columns]

# Mencari nilai k optimal menggunakan Elbow Method
max_k = 10
find_optimal_k_elbow(X, max_k)

# Mencari nilai k optimal menggunakan Silhouette Score
find_optimal_k_silhouette(X, max_k)
```


```python
from sklearn.cluster import KMeans
from sklearn.metrics import silhouette_score

# Function to find optimal k using the Elbow Method
def find_optimal_k_elbow(X, max_k):
    inertias = []
    for k in range(1, max_k + 1):
        kmeans = KMeans(n_clusters=k, random_state=42)
        kmeans.fit(X)
        inertias.append(kmeans.inertia_)

    # Plot Elbow graph
    plt.figure(figsize=(8, 6))
    plt.plot(range(1, max_k + 1), inertias, marker='o')
    plt.xlabel('Number of clusters (k)')
    plt.ylabel('Inertia')
    plt.title('Elbow Method')
    plt.show()

    # Return the fitted KMeans model with optimal k
    optimal_k = np.argmin(np.diff(inertias)) + 2
    kmeans = KMeans(n_clusters=optimal_k, random_state=42)
    kmeans.fit(X)
    return kmeans

# Function to find optimal k using the Silhouette Score
def find_optimal_k_silhouette(X, max_k):
    silhouette_scores = []
    for k in range(2, max_k + 1):
        kmeans = KMeans(n_clusters=k, random_state=42)
        kmeans.fit(X)
        labels = kmeans.labels_
        silhouette_scores.append(silhouette_score(X, labels))

    # Plot Silhouette Score graph
    plt.figure(figsize=(8, 6))
    plt.plot(range(2, max_k + 1), silhouette_scores, marker='o')
    plt.xlabel('Number of clusters (k)')
    plt.ylabel('Silhouette Score')
    plt.title('Silhouette Score')
    plt.show()

    # Return the fitted KMeans model with optimal k
    optimal_k = np.argmax(silhouette_scores) + 2
    kmeans = KMeans(n_clusters=optimal_k, random_state=42)
    kmeans.fit(X)
    return kmeans


selected_columns = ['MonthlyIncome', 'Age', 'DailyRate']
X = df2[selected_columns]

# Mencari nilai k optimal menggunakan Elbow Method
max_k = 10
kmeans_model = find_optimal_k_elbow(X, max_k)

# Predict cluster labels and add 'label' column to the DataFrame
df2['label'] = kmeans_model.predict(X)

df2

```


```python
from mpl_toolkits.mplot3d import Axes3D

# 3D Visualization of the Clusters
fig = plt.figure(figsize=(10, 8))
ax = fig.add_subplot(111, projection='3d')

# Create a colormap for the clusters
colors = plt.cm.tab10(df2['label'] / float(max(df2['label'])))

# Plot the data points
ax.scatter(df2['MonthlyIncome'], df2['Age'], df2['DailyRate'], c=colors, s=50)

# Set labels for the axes
ax.set_xlabel('MonthlyIncome')
ax.set_ylabel('Age')
ax.set_zlabel('DailyRate')

# Set the title
ax.set_title('Employee Cluster')

plt.show()
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    File ~\AppData\Local\anaconda3\lib\site-packages\pandas\core\indexes\base.py:3802, in Index.get_loc(self, key, method, tolerance)
       3801 try:
    -> 3802     return self._engine.get_loc(casted_key)
       3803 except KeyError as err:
    

    File ~\AppData\Local\anaconda3\lib\site-packages\pandas\_libs\index.pyx:138, in pandas._libs.index.IndexEngine.get_loc()
    

    File ~\AppData\Local\anaconda3\lib\site-packages\pandas\_libs\index.pyx:165, in pandas._libs.index.IndexEngine.get_loc()
    

    File pandas\_libs\hashtable_class_helper.pxi:5745, in pandas._libs.hashtable.PyObjectHashTable.get_item()
    

    File pandas\_libs\hashtable_class_helper.pxi:5753, in pandas._libs.hashtable.PyObjectHashTable.get_item()
    

    KeyError: 'label'

    
    The above exception was the direct cause of the following exception:
    

    KeyError                                  Traceback (most recent call last)

    Cell In[299], line 8
          5 ax = fig.add_subplot(111, projection='3d')
          7 # Create a colormap for the clusters
    ----> 8 colors = plt.cm.tab10(df2['label'] / float(max(df2['label'])))
         10 # Plot the data points
         11 ax.scatter(df2['MonthlyIncome'], df2['Age'], df2['DailyRate'], c=colors, s=50)
    

    File ~\AppData\Local\anaconda3\lib\site-packages\pandas\core\frame.py:3807, in DataFrame.__getitem__(self, key)
       3805 if self.columns.nlevels > 1:
       3806     return self._getitem_multilevel(key)
    -> 3807 indexer = self.columns.get_loc(key)
       3808 if is_integer(indexer):
       3809     indexer = [indexer]
    

    File ~\AppData\Local\anaconda3\lib\site-packages\pandas\core\indexes\base.py:3804, in Index.get_loc(self, key, method, tolerance)
       3802     return self._engine.get_loc(casted_key)
       3803 except KeyError as err:
    -> 3804     raise KeyError(key) from err
       3805 except TypeError:
       3806     # If we have a listlike key, _check_indexing_error will raise
       3807     #  InvalidIndexError. Otherwise we fall through and re-raise
       3808     #  the TypeError.
       3809     self._check_indexing_error(key)
    

    KeyError: 'label'



    
![png](output_82_1.png)
    



```python

```
