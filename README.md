# HR Analytics on Absenteeism and Health
Goal: Evaluating an HR dataset about absenteeism and health. To determine how to provide a bonus and incentive to healthy employees.

# Introduction:

![image1](https://github.com/Winxent/HR-Analytics-on-Absenteeism-and-Health/assets/146320825/821a862b-bf6a-40f3-a65b-372318a9fabf)

![rainbow](https://github.com/Winxent/portfolio/assets/146320825/5dc438d2-e138-4db0-97a0-e5ae8c3473e8)

# Dashboard (PowerBI)
For interactive visualisation: 
https://app.powerbi.com/reportEmbed?reportId=571161c0-2747-44d8-91e3-f6f8ae29b242&autoAuth=true&ctid=3a59e355-01e4-45dc-af92-5796b392d9f5

![image4](https://github.com/Winxent/HR-Analytics-on-Absenteeism-and-Health/assets/146320825/da29fc17-3764-48d9-9210-5822cafb289b)

![rainbow](https://github.com/Winxent/portfolio/assets/146320825/5dc438d2-e138-4db0-97a0-e5ae8c3473e8)

# Summary

## 1. To find the list of healthy employees


Set query as below:


select * from Absenteeism_at_work
where Social_drinker = 0 and Social_smoker = 0
and Body_mass_index < 25 and 
Absenteeism_time_in_hours < (select AVG(Absenteeism_time_in_hours) from Absenteeism_at_work)


Or 


select id,Social_drinker,Social_smoker,Body_mass_index,Absenteeism_time_in_hours, (select AVG(Absenteeism_time_in_hours) from Absenteeism_at_work) as average from Absenteeism_at_work
where Social_drinker = 0 and Social_smoker = 0
and Body_mass_index < 25 and 
Absenteeism_time_in_hours < (select AVG(Absenteeism_time_in_hours) from Absenteeism_at_work);

![image3](https://github.com/Winxent/HR-Analytics-on-Absenteeism-and-Health/assets/146320825/da24cb92-4adf-4d83-ae84-dfbb4c230e4e)

#### Total we have 111 healthy employees eligible for healthy bonus:
#### Therefore, each employees entitled for $9 USD bonus for the budget of $1000 USD

## 2. To find the wage increase for non smoker employees


Set query as below:


select count (*) as nonsmokers from Absenteeism_at_work
where Social_smoker =0;


![image2](https://github.com/Winxent/HR-Analytics-on-Absenteeism-and-Health/assets/146320825/acadc8e9-5912-4f1d-ae80-c8e00ab4060e)


#### This query found out there are 686 non smoker employees eligible for insurance budget of $983,221 USD. assuming 5 working days with 8 working hour and 52 weeks, per employee entitle for an additional $0.68 wage raise per hour.

## 3. Create a dashboard with the below approved wireframe 

![image6](https://github.com/Winxent/HR-Analytics-on-Absenteeism-and-Health/assets/146320825/3418732d-6d35-40ce-a6e4-58bd4212e191)

Dashboard refer to the link below or DASHBOARD

https://app.powerbi.com/reportEmbed?reportId=571161c0-2747-44d8-91e3-f6f8ae29b242&autoAuth=true&ctid=3a59e355-01e4-45dc-af92-5796b392d9f5





