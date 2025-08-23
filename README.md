# Data Jobs Dashboard  

This Power BI dashboard provides insights into the demand and compensation trends for data-related roles.  
It consolidates job postings data to highlight job availability, salary comparisons, and growth patterns across different job titles in the data industry.  

The dashboard is designed to help users quickly understand:  

- The overall volume of data job postings  
- Median yearly and hourly salary levels  
- Monthly trends in job demand  
- Salary variations across different data roles  
- A comparison of hourly vs yearly pay for various positions  
- Long-term salary movements using sparklines  

## Dataset  

The data for this dashboard comes from the following source:  

- **Hugging Face Dataset:** [lukebarousse/data_jobs](https://huggingface.co/datasets/lukebarousse/data_jobs)  

This dataset contains job postings related to data roles, including job titles, salaries (hourly and yearly), and posting dates.  
It was cleaned and transformed before being loaded into Power BI for visualization. 

--------------------
## Tools & Technologies Used  

This project was built using a combination of data transformation, analysis, and visualization tools. Each played a key role in preparing, processing, and presenting insights:  

### 1. Power Query  
- Used inside **Power BI** for initial data cleaning and preprocessing.  
- Changed data types to appropriate formats (e.g., dates, numbers, text).  
- Replaced `NaN` / null values with defaults or meaningful replacements.  
- Filtered irrelevant rows and standardized column naming conventions.  
- Merged datasets
- Created Datasets from the main data source like `skills_dim`,`skills_job_dim`.
- Unpivoted `skill_jobs` for skills analysis.

### 2. DAX (Data Analysis Expressions)  
- Created calculated measures and columns for advanced metrics.  
- Built dynamic KPIs such as:  
  - Median salaries by role  
  - Adjusted yearly salaries (hourly × 2080)  
  - Percentage of postings offering remote work, health insurance, etc.  
- Implemented **field parameters** to enable interactive switching between measures.  
- Designed drill-through functionality for job-specific analysis.  

### 3. Python  
- Integrated via **Power BI Python Script Editor** for advanced data analysis and custom visuals.  
- Exploded lists (e.g., `job_skills`) into rows for skill-based salary analysis.  
- Performed groupby aggregations and median calculations by role and skill.  
- Created custom visualizations with **Seaborn** and **Matplotlib** (e.g., Junior vs Senior salary by skills).  

### 4. Power BI Desktop  
- Built interactive dashboards and drill-through pages.  
- Created visuals such as bar charts, scatter plots, maps, and trend analyses.  
- Designed an intuitive layout with slicers and filters for user interaction.  
- Integrated multiple pages for both **overview dashboards** and **detail pages**.  

### 5. Git & GitHub  
- Version control to track progress and maintain reproducibility.  
- Repository hosts the project files, Python scripts, and `README.md` documentation.  
- Enables collaboration and sharing of the project.  

---

This combination of tools allowed me to **clean**, **transform**, **analyze**, and **visualize** the dataset efficiently, while ensuring the insights were both accurate and interactive.  


## Dataset Details  

The dataset includes the following columns:  

- **job_title_short**: Simplified or standardized job title  
- **job_title**: Original job title as listed in the posting  
- **job_location**: Location of the job posting  
- **job_via**: Platform or source where the job was posted  
- **job_schedule_type**: Type of employment (full-time, part-time, contract, etc.)  
- **job_work_from_home**: Indicates if the role is remote/work-from-home  
- **search_location**: Geographical location used for data search  
- **job_posted_date**: Date when the job was posted  
- **job_no_degree_mention**: Whether the posting mentions a degree requirement  
- **job_health_insurance**: Whether health insurance is offered  
- **job_country**: Country of the job posting  
- **salary_rate**: Salary type (e.g., yearly, hourly)  
- **salary_year_avg**: Average yearly salary (normalized)  
- **salary_hour_avg**: Average hourly salary (normalized)  
- **company_name**: Name of the hiring company  
- **job_skills**: List of skills mentioned in the posting  
- **job_type_skills**: Categorization of skills by type (technical, analytical, etc.)  

## Dashboard Details  

The **Data Jobs Dashboard** is designed to analyze job postings in the data industry and highlight hiring trends, salary insights, and role-specific details.  
It is divided into the following key components:  

### 1. Key Performance Indicators (KPIs)  
At the top of the dashboard, three key metrics provide a quick snapshot of the overall dataset:  

- **Job Count:** Total number of job postings (479K).  
- **Median Yearly Salary:** The central yearly salary across roles ($113.25K).  
- **Median Hourly Salary:** The central hourly salary across roles ($47.62).  

These KPIs give users an immediate sense of the job market size and pay scales.  

---

### 2. Job Postings by Month  
This line chart shows the **monthly distribution of job postings** across the year.  

- Peaks in hiring can be observed in **January, February, and August**, with job counts above 47K.  
- A decline occurs toward the end of the year, with the lowest postings in **November and December**.  
- This trend highlights potential seasonality in hiring for data-related roles.  


### 3. Hourly vs Yearly Salary Comparison  
This scatter plot compares **median yearly salaries** against **median hourly salaries** for different job titles.  

- Roles like **Software Engineer** and **Machine Learning Engineer** show both higher yearly and hourly salaries.  
- Mid-range roles such as **Data Engineer** and **Senior Data Analyst** are plotted in the middle salary ranges.  
- Entry-level positions like **Data Analyst** appear on the lower end of the salary distribution.  
- Yearly salary and hourly salary are correlated.

This visual allows comparison between hourly and annual compensation, offering insight into how different data roles are valued.  


### 4. Highest Paying Jobs in Data  
This bar chart highlights the **top-paying data-related roles**.  

- **Senior Data Scientist** and **Machine Learning Engineer** lead with the highest median yearly salaries, both approaching $160K.  
- Other high-paying roles include **Senior Data Engineer** and **Software Engineer**.  
- Business-oriented roles such as **Business Analyst** rank lower in terms of salary.  

This view is useful for job seekers to understand which roles offer the most competitive pay.  


### 5. Median Salaries with Sparklines  
This table lists **median yearly salaries** for different job titles along with sparklines to show **salary movements over time**.  
  
- Sparklines allow users to quickly identify whether salaries for each role are stable, increasing, or decreasing.  
- The overall median yearly salary across all jobs is about **$113,250**.  


### Summary  
Together, these visuals provide a comprehensive overview of:  

- **Market demand** (job postings trends)  
- **Compensation levels** (KPIs, highest paying roles)  
- **Pay structures** (hourly vs yearly comparison)  
- **Role-specific salary patterns** (sparklines and detailed drill-through)  

This combination makes the dashboard valuable both for **job seekers** exploring opportunities and for **analysts** studying hiring trends in the data industry.  
 

![Data Jobs Dashboard](/Dashboard.png) 


## Drill-Through Page  

The dashboard supports **drill-through functionality**, where selecting a specific job title opens a dedicated detail page.  

For example, drilling through on **Data Analyst** shows:  

- **Salary Overview**  
  - Median yearly salary  
  - Median hourly salary  

- **Work Conditions**  
  - Percentage of roles offering remote (work from home) options  
  - Percentage of postings requiring a degree  
  - Percentage of postings offering health insurance  

- **Geographic Distribution**  
  - A global map highlighting where the roles are located  

- **Job Platforms**  
  - Breakdown of postings across different job platforms (e.g., LinkedIn, Indeed, ZipRecruiter)  

- **Job Schedule Type**  
  - Distribution of full-time, part-time, contract, internship, and temporary roles  


This drill-through view allows users to analyze one role in depth 


![Data Jobs Dashboard](/Drill_through.png) 


## Adjusted Yearly Salary Analysis  

In addition to the main dashboard, an extended analysis was performed to compare the **average yearly salary** provided in the dataset with an **adjusted yearly salary** derived from hourly wages.  

### Calculation  
The adjusted yearly salary was calculated using the formula:  

**Adjusted Yearly Salary** = **salary_hour_avg** × 2080

![Data Jobs Dashboard](/Yearly_salary%20vs%20Adjusted.png) 



Here, `2080` represents the standard number of working hours in a year (40 hours per week × 52 weeks).  

### Visuals  

- **Bar Chart:**  
  Compares the reported yearly salary (`salary_year_avg`) with the adjusted yearly salary for each job role.  
  This helps identify discrepancies between roles where hourly rates may suggest a higher or lower annual income than what is reported.  

- **Scatter Plot (Right):**  
  Plots yearly salary against adjusted yearly salary.  

  - Jobs positioned **away from the line** (e.g., Data Analyst, Business Analyst) Yearly salary and adjusted yearly salary.  
 
Across **all roles**, the adjusted yearly salary is consistently **less than the reported yearly salary**.  
- This trend suggests that **companies prefer offering employees yearly contracts**, where salaries are higher than what an hourly rate would imply.  

This analysis ensures that the salary data is validated and provides a more realistic view of annual compensation based on hourly pay rates, while also uncovering hiring preferences in the job market.  


## Median Salary by Job Schedule  

This visualization shows the **median salary distribution across different job schedule types**. 

![Median Salary by Job Schedule](/Salary_by_job_schedules.png)

### Key Findings  
- **Part-Time roles** surprisingly report the highest median salary, slightly above **$120K**, which may reflect specialized consulting or high-demand skills offered on a reduced schedule.  
- **Full-Time positions** rank second, with a median salary of around **$112K**, showing that stable, long-term contracts remain highly competitive.  
- **Contractor roles** follow closely with salaries above **$100K**, emphasizing the value of short-term, project-based expertise.  
- **Temporary work (Temp Work)** and **Per Diem** jobs earn between **$75K–$85K**, reflecting flexible or on-demand work arrangements.  
- **Internships** report the lowest salaries (around **$50K**), which is expected due to the entry-level nature of these roles.  

### Insights  
This analysis reveals that while full-time employment remains attractive, **non-traditional work arrangements such as part-time and contracting can often yield higher salaries**, especially in data-related fields where niche expertise is valued.  

## Median Salary vs Skills Per Job  

This scatter plot explores the relationship between the **median salary** of a role and the **average number of skills required per job posting**.  

![Median Salary vs Skills Per Job](/Skillperjob.png) 

### Key Observations  
- **Senior Data Engineer** demands the highest number of skills (around 7 on average) and also offers one of the highest median salaries (~$155K).  
- **Machine Learning Engineer**, **Software Engineer**, and **Senior Data Scientist** fall in the high-skill, high-salary quadrant, confirming that specialized expertise drives salary.  
- **Data Engineer** also shows a high skills-per-job requirement (~6 skills), coupled with strong salary (~$125K median).  
- Roles like **Data Analyst** and **Business Analyst** require fewer skills (around 3–4) and are positioned with lower salaries ($90K–$100K range).  
- The dotted trendline suggests a **positive correlation between the number of skills required and salary**: the more skills a job demands, the higher the pay tends to be.  

### Insights  
This analysis highlights that **technical complexity and skill breadth directly influence salary in data jobs**. Senior and engineering-focused roles require deeper technical expertise, which is reflected in higher salary levels.  
 


## Parameter-Based Visual Analysis  

This visual is built with **dynamic X and Y parameters**, allowing flexible analysis of different aspects of the dataset.  
The chart updates automatically based on the selected fields.  


![Dynamic Parameter Visual](/Field_Parameter.png)  


### Key Features  
- **Y-Parameter Options**  
  - Job Country  
  - Job Title  
  - Skills  

- **X-Parameter Options**  
  - Median Salary  
  - Skill Count  
  - Job Count  


### Why It’s Useful  
This dynamic visual provides a **flexible exploration tool** that enables users to analyze:  
- How salaries differ across job titles,skills or countries.  
- Which skills are most frequently required in the job market.  



## Junior vs Senior Salary by Skills  

This analysis compares the **median yearly salaries** of *Data Analysts* and *Senior Data Analysts* across the top 10 most frequently mentioned skills in job postings.  

![Junior vs Senior Data Analyst Salary by Skill](/Senior_vs_Junior.png)

### Methodology  
- The dataset was filtered to include only **Data Analyst** and **Senior Data Analyst** roles.  
- The `job_skills` column, which contains lists of skills, was expanded using `explode`.  
- Median yearly salaries were calculated separately for each skill by role.  
- The results were reshaped into long format and visualized as a grouped bar chart.  
- Skills were ordered by **Senior Analyst median salary (descending)** for better interpretation.

## Python Code  

The following Python script was used to generate the visualization comparing **Data Analyst** and **Senior Data Analyst** salaries by skills. 

<details>
<summary>Show Code</summary>

```python
import pandas as pd
import matplotlib.pyplot as mplp
import seaborn as sns
import ast

# dataset = pandas.DataFrame(job_title_short, salary_year_avg)
# dataset = dataset.drop_duplicates()

data = dataset
jr = ['Data Analyst', 'Senior Data Analyst']
dataa = data[data.job_title_short.isin(jr)]
dataa['job_skills'] = dataa.job_skills.apply(lambda x: ast.literal_eval(x) if pd.notna(x) else x)

dj = dataa[dataa.salary_year_avg.notna()].explode('job_skills')

tts = dj.job_skills.value_counts().head(10).index.to_list()
abd = dj[dj.job_title_short=='Data Analyst'].groupby('job_skills')['salary_year_avg'].median().reset_index().rename(columns={'salary_year_avg':'Junior Salary'})
abd1 = dj[dj.job_title_short=='Senior Data Analyst'].groupby('job_skills')['salary_year_avg'].median().reset_index().rename(columns={'salary_year_avg':'Senior Salary'})
abd2 = abd.merge(abd1,on='job_skills',how='left')

df_melted = abd2[abd2.job_skills.isin(tts)].melt(
    id_vars="job_skills",
    value_vars=["Junior Salary", "Senior Salary"],
    var_name="Seniority",
    value_name="Salary"
)

order = (
    abd2[abd2.job_skills.isin(tts)]
    .sort_values("Senior Salary", ascending=False)["job_skills"]
    .tolist()
)

mplp.figure(figsize=(10,6))
sns.barplot(
    data=df_melted,
    y="job_skills",
    x="Salary",
    hue="Seniority",
    order=order
)
mplp.title("Junior vs Senior Salary by Skill")
mplp.xlabel("Median Salary")
mplp.ylabel("Job Skills")
mplp.show()
```
</details>  

### Visualization  
The chart shows two bars for each skill: one representing the median salary for **Data Analysts**, and the other for **Senior Data Analysts**.  

- Senior roles consistently earn more across all skills.  
- Certain skills (such as SQL, Python, or Tableau) are associated with higher salaries.  
- Ordering by Senior Analyst salary highlights which skills command the greatest pay premium.  

This visualization provides insight into how **specific skills influence salary levels** within junior and senior analyst positions.  


### Final Conclusions  

This project highlights key insights into the data job market using a combination of Power BI, DAX, Python, and Power Query.  

- **High-paying roles** such as *Senior Data Scientist*, *Machine Learning Engineer*, and *Senior Data Engineer* consistently top the salary charts, showing strong demand for advanced technical expertise.  
- **Entry-level roles** like *Data Analyst* and *Business Analyst* have comparatively lower salaries, but they remain highly sought-after positions with broad demand across industries.  
- The **adjusted yearly salary analysis** revealed that reported yearly salaries are often higher than what hourly rates suggest, indicating that companies prefer offering fixed yearly contracts.  
- **Job schedule analysis** shows that part-time and contractor roles can sometimes yield higher salaries than traditional full-time positions, reflecting the premium for flexibility and specialized expertise.  
- The **skills vs salary analysis** confirmed a positive correlation between the number of skills required and salary levels, with engineering and senior roles demanding broader skill sets.  
- Skill-specific analysis for *Data Analysts* vs *Senior Data Analysts* demonstrated that senior roles consistently offer higher salaries across all major skills, with SQL, Python, and Tableau standing out as high-value skills.  

Overall, this project demonstrates how combining **interactive dashboards** with **custom Python visuals** and **data modeling in DAX** can provide both high-level overviews and deep, skill-specific insights into the job market. It shows not only the **current state of salaries and demand in data jobs**, but also the **skills and work arrangements that drive higher pay**.  
