# NewGlobe_case_study
This case study demeontres my ability to perform common data tasks such as cleaning , KPI contruction , descriptive analysis and  and data modeling


***Case study - Analyst***
Step 1: Data cleaning (~45 min)
Please create a file at the student-level which has information about their test scores, school information, their attendance, and their teacher’s lesson completion rate. Note that this is the main data set that we expect you to share with us.
Hint: note that the four data sets you will use are all presented at different “levels” of the data (e.g., “School information” is at the level of the school, but “Pupil scores” is at the level of the student). Therefore, we suggest that you start by reshaping the “Pupil scores” file so that each student only has one row in the data, with different columns for their scores in math, fluency, and Kiswahili. Use this as your “base file”, and start merging all the other files to this. Be careful with how you merge things: since there are many students to a school or even a teacher, some of these merges will need to be “many-to-one” (but not all). 

 
**Step 2: Calculating KPIs***
One of our main KPIs within the Schools Vertical is “Percent Pupils Present”. The “layman’s definition” of this KPI is “The percentage of pupils who were present, out of all pupils - across all days in the term to date ”. In other words,  the percentage of pupils who were present (for each pupil in the “Pupil attendance” file, this is displayed in the “present_records” variable), out of pupils who had attendance records (the “attendance_records” variable in the same file).
●	The first task is to translate this KPI into the data. We will calculate this KPI in two different ways. First, calculate this KPI for all pupils at once. What is the network-level average Percent Pupils Present (use two decimal points)? 
●	Now, please calculate this percentage for each school, and create an average at the school-level. What is the average Percent Pupils Present now (use two decimal points)?
●	How does the interpretation of the KPI change between the two approaches? Does it matter in this case? When would it matter, (i.e., when would one be more appropriate than the other?) 2-4 sentences max.

Sub report from   analysis
1)When I used the first approach to  calculating the “Percent Pupils Present” I found that the network-average Percent Pupils Present is 76 % when rounded to two decimals . This could be interpreted as the fact that  bridge Kenya  program recorded across  all the pupils an estimation of the  Percent Pupils Present as  76% .
 
2) Afterwards I calculated the percentage for each school and averaged it at the school level. The average Percent Pupils Present now is still 76%.
3)The interpretation of the  KPI between the two approaches is that for the second approach  it can be inferred that this KPI is an estimation of Percent Pupils Present across schools  whereas  the first approach gives us  the Percent Pupil present across pupils.
4)I don’t think it matters because the two approaches give us the same  estimation.


**Step 3: Descriptives analysis***
Let’s dig into the reading fluency scores in your current data set. These came from the “Pupil scores” data, but you will need the data set you created in Step 1 above to answer these questions. Please answer the following questions as succinctly as possible.
●	Please create a figure or a table, whichever you prefer, which shows average fluency scores for each of the five grades. 
●	Which regions (using the “region” variable) have the lowest and highest average fluency score across all grades? 
●	Please create a binary variable that is 1 if a given child reads at 10 or lower, and 0 otherwise. Please create a bar chart with grades on the x-axis, and the share of pupils scoring under this threshold for each grade. 
●	What school has the highest share of pupils scoring under this threshold in grade 3?


Sub-report from  analysis
Grades	 Average Fluency score
Grade 1	53.16521
Grade2	104.43394
Grade 3	127.02271
Grade 4	145.47334
Grade 5	154.75989

This table above shows the average fluency score across all the 5 grades in the data 

From the the output we see that The Kirinvaga region  has the lowest average fluency score with an average fluency score equals to 60.31 . The Machkos region  has the highest average fluency score with an average fluency score equals to 157.76



 Grades 	Share of pupils that reads at 10 or lower 
Grades 1	0.110
Grade 2	0.034
Grade 3	0.022
Grade 4	0.0166
Grade 5	0.0091

This table above shows the share of pupils that reads  at 10 or lower across  all he grades 


 

![image](https://github.com/user-attachments/assets/a3c82820-5362-4b46-831f-6b5c58cc7f17)





This bar chart shows the  share of pupils that reads  at 10 or lower across all  the 5 grades in the data 
We see  from this bar chart that the share of pupils that reads at 10 or lower  goes down from grade 1 to grade 5
What we see here is quite normal since pupils tend to get  better at reading as they progress through grades.

 I found that the school with the highest share of pupils that read at 10 and lower is the school with the identification number( 223941 in the data set). With roughly 34%  of its grade 3 kids who reads at 10 or lower.  



***Step 4: Impact evaluation***
During this term, we rolled out an intensive after-school tutoring program in 55 schools. The selection to be a part of the 55 schools was randomly assigned - in other words, these schools were part of a randomized controlled trial (RCT). The “School Information” data set has a binary variable for whether each school was part of the program or not. 
●	Our Chief Academic Officer would like to know whether this program had any effects on test scores in math, Kiswahili, fluency, and/or student attendance. Please conduct any calculations you see fit to answer his questions. 
●	After conducting the impact evaluation, we have heard anecdotally that teachers in schools that received tutoring felt more motivated and were completing their lessons at a faster pace. Hence, we could worry that the effects that we see are not (solely) due to the tutoring program, but also due to the higher lesson completion rate. Does this hypothesis hold up in the data?



Table 1
Outcome : score fluency

                 Estimate Std. Error t value Pr(>|t|)    
(Intercept)        97.779      3.923  24.927  < 2e-16 ***
tutoring_program   33.788      5.573   6.063 1.96e-08 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 29.35 on 109 degrees of freedom
Multiple R-squared:  0.2522,	Adjusted R-squared:  0.2454 
F-statistic: 36.76 on 1 and 109 DF,  p-value: 1.956e-08

We see from this regression table 1 that pupils in the schools where teachers were trained tend to read at 33 points more than pupils in the schools that did not take part in the tutoring program.. This can allow us to state that the tutoring program has a significant impact on pupils’ reading abilities.

Table 2
outcome: Math score

                 Estimate Std. Error t value Pr(>|t|)    
(Intercept)      0.716377   0.008829   81.14   <2e-16 ***
tutoring_program 0.028595   0.012542    2.28   0.0246 *  
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.06607 on 109 degrees of freedom
Multiple R-squared:  0.04552,	Adjusted R-squared:  0.03676 
F-statistic: 5.198 on 1 and 109 DF,  p-value: 0.02456

We see from this table 2 that kids in the schools where the teacher participated in the tutoring program tend to have on average 0.02 more scores than the ones in schools where teachers did not receive the training. This result allows us to conclude that the tutoring Program has a significant  impact on pupils’ math scores  


Table 3
Outcome :Score Kiswahili

                 Estimate Std. Error t value Pr(>|t|)    
(Intercept)      0.689074   0.009598  71.797  < 2e-16 ***
tutoring_program 0.118810   0.013635   8.714 3.61e-14 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.07182 on 109 degrees of freedom
Multiple R-squared:  0.4106,	Adjusted R-squared:  0.4052 
F-statistic: 75.93 on 1 and 109 DF,  p-value: 3.611e-14

This table shows that pupils in the schools   where teachers received the  tutoring program tend to score 0.11 in Kiswahili more on average than the ones in the schools where the teachers did not participate in the program. Thus it can be inferred there is evidence that the tutoring program has a significant impact on Kiswahili scores of the pupils.



We are now interested in knowing whether the tutoring program has any significant impact on lesson completion rates
Table 4
      Outcome : lesson completion rates

            Estimate Std. Error t value Pr(>|t|)    
(Intercept)       0.600111   0.020269  29.607   <2e-16 ***
tutoring_program -0.001936   0.028795  -0.067    0.947    
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.1517 on 109 degrees of freedom
Multiple R-squared:  4.146e-05,	Adjusted R-squared:  -0.009132 
F-statistic: 0.00452 on 1 and 109 DF,  p-value: 0.9465

From this table above  we see that there is  no any significant correlation between the program and the lesson completion rates
Hence we can  conclude that  this motivation of the teachers that came from the anecdote  may not be caused by the fact that they received the training .




Table 5
         Outcome :score kiswahili  

                    Estimate Std. Error t value Pr(>|t|)    
(Intercept)                     0.64708    0.02867  22.566  < 2e-16 ***
tutoring_program                0.11895    0.01355   8.780 2.73e-14 ***
lesson_completion_rate_average  0.06998    0.04506   1.553    0.123    
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.07136 on 108 degrees of freedom
Multiple R-squared:  0.4235,	Adjusted R-squared:  0.4128 
F-statistic: 39.66 on 2 and 108 DF,  p-value: 1.215e-13




Table 6
Outcome : fluency score

                               Estimate Std. Error t value Pr(>|t|)    
(Intercept)                      99.299     11.849   8.380 2.15e-13 ***
tutoring_program                 33.783      5.598   6.035 2.28e-08 ***
lesson_completion_rate_average   -2.533     18.621  -0.136    0.892    
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 29.49 on 108 degrees of freedom
Multiple R-squared:  0.2523,	Adjusted R-squared:  0.2385 
F-statistic: 18.23 on 2 and 108 DF,  p-value: 1.513e-07


Hypothesis verification
From the Tables 5 and 6 we see that when we control for the lesson completion rates variable we do not see any significant  correlation between lesson completion   rates and test scores ( Kiswahili and reading scores) . We  can then  inform  the Academic officer that the  tutoring program could have a causal impact on  Kiswahili and reading scores whereas this conclusion may not hold for the score in math since we see a significant correlation between lesson completion  rates and math scores (which comes from Table 7 below ).


Table 7
     Outcome :math  score 
 
                    Estimate Std. Error t value Pr(>|t|)    
(Intercept)                     0.66918    0.02623  25.510   <2e-16 ***
tutoring_program                0.02875    0.01239   2.320   0.0222 *  
lesson_completion_rate_average  0.07864    0.04122   1.908   0.0591 .  
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.06528 on 108 degrees of freedom
Multiple R-squared:  0.07663,	Adjusted R-squared:  0.05954 
F-statistic: 4.482 on 2 and 108 DF,  p-value: 0.01349













