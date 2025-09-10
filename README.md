# The Analysis

## 1. What are the most demanded skills for the top 3 most popular data roles? To

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