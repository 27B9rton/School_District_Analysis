# School_District_Analysis
## Project Overview
This analysis was done for a School Board to see passing rates and trends for a school district. The data was cleaned and passing percentages for reading/math/overall were found for students by grade, by school, by school type, and district-wide averages. The initial code needed to be refactored to remove Thomas High School's 9th grade class, which had data integrity issues.

## Summary Findings

### Top Performers
The Top 5 schools in Overall Passing percentage were:
  - Cabrera High School	91.33 %
  - Thomas High School	90.63 %
  - Griffin High School	90.59 %
  - Wilson High School	90.58 %
  - Pena High School		90.54 %

All 5 of these top performers were Charter Schools.

### Bottom Performers
  - Rodriguez High School	52.98 %
  - Figueroa High School	53.20 %
  - Huang High School   	53.51 %
  - Hernandez High School	53.52 %
  - Johnson High School	  53.53 %

All 5 bottom performers were public (District) schools.
This data is supported when we break the data into passing rate by school type as well. Here's the code I used. 

          type_summary_df = pd.DataFrame({
                    "Average Math Score" : type_math_scores,
                    "Average Reading Score": type_reading_scores,
                    "% Passing Math": type_passing_math,
                    "% Passing Reading": type_passing_reading,
                    "% Overall Passing": type_overall_passing})
          type_summary_df["Average Math Score"]=type_summary_df["Average Math Score"].map("{:.1f}".format)
          type_summary_df["Average Reading Score"] = type_summary_df["Average Reading Score"].map("{:.1f}".format)
          type_summary_df["% Passing Math"] = type_summary_df["% Passing Math"].map("{:.0f}".format)
          type_summary_df["% Passing Reading"] = type_summary_df["% Passing Reading"].map("{:.0f}".format)
          type_summary_df["% Overall Passing"] = type_summary_df["% Overall Passing"].map("{:.0f}".format)


          type_summary_df


That code gives us this output:
        	Average Math Score	Average Reading Score	% Passing Math	% Passing Reading	% Overall Passing

School Type					
          Charter	83.5	83.9	94	97	90
          District	77.0	81.0	67	81	54
          
## Passing Rates by School Spending and School Size
Interestingly, despite the top 5 performing schools all being Charter schools, the data does not show that spending more per student correlates with a bettter passing rate. The group spending less than $586 per student(which is the smallest amount) actually scored the highest on the overall passing percentage.

From the Size Summary, it does seem that as schools get larger, the passing percentage starts to shrink, especially in math between Medium and Large sized schools.

### Overall Summary
Among the 15 schools and 39, 170 students:
- The Average Math score was 78.9 %
- The Average Reading score was 81.9 %
- 74.8 % of students were passing Math
- 85.7 % of students were passing Reading
- 64.9% of students were passing both Math and Reading

# Thomas High School Findings
9th graders scores at Thomas High School (THS) were replaced.
Originally, THS had 83% of students passing math. That number jumped to 93% when the 9th grade scores were discounted.
THS also had 83% of students passing reading. That number changed to 97 % with no 9th grade scores.
THS had almost no change in the total % passing when the 9th grade scores were removed. 

### THS 9th Grade Scores Removed

Removing the 9th grade scores from THS slightly lowered the overall passing %, the % passing reading, and the % passing math for the entire District.


Removing the 9th grade scores from THS had little to no effect on the Scores by school spending.
Removing the 9th grade scores from THS shrunk the medium sized school % overall passing by nearly .1%.
Removing the 9th grade scores from THS had little to no effect on the Scores by school type.


