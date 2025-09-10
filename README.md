# The Analysis

## 1. What are the most demanded skills for the top 3 most popular data roles? 

To find the most demanded skills for the top 3 most popular data roles. I filtered out those positions by which ones were the most popular, This query highlights th most popular job titles and their top skills, showing which skills I should pay attention to depending on the role I'm targeting. 

View my notebook with detailed steps here : [2_Skill_Demand.ipynb](Project\2_Skill_Demand.ipynb)

### Visualize Data
```python
fig, ax = plt.subplots(len(job_titles),1)

for i, job_title in enumerate(job_titles):
    df_plot = df_skill_percent[df_skill_percent['job_title_short']==job_title].head(5)
   
    sns.barplot(data=df_plot,x='skill_percent',y='job_skills', ax=ax[i], hue='skill_count')
    plt.show()
```
### Results
![Visualization of Top Skills for Data Nerda](Project\images\Skill_demand_all_data_roles.png)

### Insights
- Python is a verssatile skill, highly demanded across all three roles, but most prominently for Data Scientist (72%) and Data Engineers (65%).
- SQL is the most requested skill for Data Analysts and Data Scientists, with it in over hald the job postings for both roles. For Data Engineers, Python is the most sought-after skill, appearing in 68% of job postings.
- Data Engineers require more specialized technical skills (AWS, Azure, Spark) compared to Data Analysts and Data Scientists who are expected to be proficient in more general data management and analysis tools (Excel, Tableau).

## 2. How are in-demand skills trending for Data Analysts?
To find how skills are trending in 2023 for Data Analysts, I filtered data analyst positions and grouped the skills by the month of the job postings. This got me the top 5 skills of data analysts by month, showing how popular skills were throughout 2023.
View my notebook with detailed steps here:[3_Skill_Trend.ipynb](Project\3_Skill_Trend.ipynb)

### Visualize Data
```python

df_plot = df_DA_US_perc.iloc[:,:5]
sns.lineplot(data = df_plot, dashes=False, palette='tab10')
from matplotlib.ticker import PercentFormatter
ax=plt.gca()
ax.yaxis.set_major_formatter(PercentFormatter(decimals=0))
```
### Results
![Visualization of Top Skills for Data Analysts in the US](Project\images\Trending skills for data analysts in the US.png)