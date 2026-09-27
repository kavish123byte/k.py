# ANALYSIS 
## 1. What are the most demanding skills for the top 3 roles ?
To find out the most demanded skills for the top 3 roles, I firstly filtered out the positions by which ones were the most popular,and then got the top 5 skills for these top 3 roles. This query highlights the most popular job roles along with their top 5 skills, showing on which skills I should pay attention if I am targeting one of the popular job roles.

View my notebook with detailed steps here : [skills_count.ipynb](Project/skills_count.ipynb)

### Visualize data
``` python
fig,ax = plt.subplots(len(title), 1)
for i, job in enumerate(title):
    df_plot_percentage = df_percentage[df_percentage['job_title_short'] == job].head(5)
    sns.barplot(data=df_plot_percentage, x='Percentage', y='job_skills', ax=ax[i],legend=False, hue= 'Percentage', palette='dark:b_r')
    ax[i].set_title(job)
    ax[i].set_ylabel('')
    ax[i].set_xlabel('')
    ax[i].set_xlim(0, 78)
    ax[i].set_xticks([])
    for n,v in enumerate(df_plot_percentage['Percentage']):
        ax[i].text(v+1, n, f'{int(v)}%', va= 'center')

fig.suptitle('Likelihood of skills required')
fig.tight_layout()
plt.show()
```

### Result
![Likelihood_of_skills](Project/Images/Likelihood_of_skills.png)
 ### Insights 
 ## Key Insights

* **Data Scientist:** Python is the most prominent skill (72%), followed by SQL (51%) and R (44%), highlighting a strong focus on programming, statistical analysis, and data science.
* **Data Analyst:** SQL (50%) and Excel (40%) lead, with Tableau (28%) and Python (27%) supporting data analysis, visualization, and reporting.
* **Data Engineer:** SQL (68%) and Python (64%) dominate, complemented by AWS (42%), Azure (32%), and Spark (32%), reflecting a strong focus on data infrastructure, cloud, and big-data technologies.
* **Common Skill:** **SQL** is consistently important across all three roles, making it a core technology in the data domain.
* **Role-specific focus:** Data Science emphasizes **Python and statistical tools**, Data Analytics emphasizes **SQL, Excel, and visualization**, while Data Engineering emphasizes **SQL, Python, cloud platforms, and Spark**.
* **Overall takeaway:** The visualization demonstrates that each role has a distinct technology stack, but **SQL and Python form the strongest common technical foundation across the data ecosystem**.
