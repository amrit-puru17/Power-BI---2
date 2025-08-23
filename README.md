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

# Data Jobs Dashboard  

This Power BI dashboard provides insights into the demand and compensation trends for data-related roles.  
It consolidates job postings data to highlight job availability, salary comparisons, and growth patterns across different job titles in the data industry.  

![Data Jobs Dashboard](/Dashboard.png) 


![Data Jobs Dashboard](/Drill_through.png) 
